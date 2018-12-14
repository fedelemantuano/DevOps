# Gradle builds

## Command Line

```sh
./gradlew --debug
```

## Reuse downloads from gradle wrapper

set GRADLE_USER_HOME to a folder for gradle (example: JENKINS_HOME/tools/gradle)  

## Repo Nexus
init script reference: https://docs.gradle.org/current/userguide/init_scripts.html  

Create init-script file in GRADLE_USER_HOME: "GRADLE_USER_HOME/init.d/init-script.gradle" :  

```
 /**
 * init.gradle file for build using the Nexus Repository Manager as proxy repository
 *
 * gradle plugin section
 */
 settingsEvaluated { settings ->
    settings.pluginManagement {
        resolutionStrategy {
            
        }
        repositories {
        maven {
                url 'https://nexus.corp.com/repository/mvn-corp-mirror/'
            }
        }
    }
}

/**
 * init.gradle file for build using the Nexus Repository Manager as proxy repository
 *
 * build section
 */

apply plugin:NexusRepositoryPlugin

class NexusRepositoryPlugin implements Plugin<Gradle> {

  final static String LOG_PREFIX = "init.gradle/NexusRepositoryPlugin:"

  final Closure NexusConfig = {
    maven {
      name = 'mvn-corp-mirror'
      url = 'https://nexus.corp.com/repository/mvn-corp-mirror/'
    }
    maven {
      name = 'mvn-corp-public'
      url = 'https://nexus.corp.com/repository/mvn-corp-public/'
    }
    // if required you can add further repositories or groups here
    // and they will be left intact if the name starts with standard-
    // although it is better to just add those repositories in Nexus
    // and expose them via the public group
  }

  final Closure RepoHandler = {
    all { ArtifactRepository repo ->
      if (repo.name.toString().startsWith("mvn-corp-") ) {
         println "$LOG_PREFIX $repo.name at $repo.url activated as repository."
      } else {
        if (repo instanceof MavenArtifactRepository) {
          remove repo
          println "$LOG_PREFIX $repo.name at $repo.url removed."
        } else {
          println "$LOG_PREFIX $repo.name kept (not a Maven repository)."
        }
      }
    }
  }


  void apply(Gradle gradle) {
    // Override all project specified Maven repos with standard
    // defined in here
    gradle.allprojects{ project ->
      println "$LOG_PREFIX  Reconfiguring repositories."
      project.repositories RepoHandler
      project.buildscript.repositories RepoHandler

      project.repositories NexusConfig
      project.buildscript.repositories NexusConfig
    }
  }
}
 
```
