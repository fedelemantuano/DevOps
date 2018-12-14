# SBT (scala building Tool)

SBT requires java and scala already installed  
ref: https://www.scala-lang.org/download/  
ref: https://www.scala-sbt.org/download.html  

### Install SBT on RHEL
  using yum repo:  
```bash
curl https://bintray.com/sbt/rpm/rpm | sudo tee /etc/yum.repos.d/bintray-sbt-rpm.repo
sudo yum install sbt
```  

  using yum local package:  
```bash
wget https://sbt.bintray.com/rpm/sbt-1.2.7.rpm
rpm -ivh sbt-1.2.7.rpm
```  

  using archive:  
```bash
wget https://piccolo.link/sbt-1.2.7.tgz
tar -xvzf sbt-1.2.7.tgz
```  
### Install Scala on RHEL

  using archive:  
```bash
wget https://downloads.lightbend.com/scala/2.12.8/scala-2.12.8.tgz
tar -xvzf scala-2.12.8.tgz
```  

### SBT repositories
location: .sbt/repositories
```properties  
[repositories]
local
mvn-corp-mirror: https://nexus.corp.com/repository/mvn-corp-mirror/
mvn-corp-public: https://nexus.corp.com/repository/mvn-corp-public/
raw-corp-mirror-ivy: https://nexus.corp.com/repository/raw-corp-mirror/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext]
## Originals to mirror (ivy)
#sbt-releases-repo: http://repo.typesafe.com/typesafe/ivy-releases/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext]
#sbt-plugins-repo: http://repo.scala-sbt.org/scalasbt/sbt-plugin-releases/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext]
```  
### SBT OPTS

|file opts|java opts|
| -------:|:--------|
|-no-colors|-Dsbt.log.noformat=true|
|-no-global|-Dsbt.global.base=$(pwd)/project/.sbtboot|
|-sbt-boot|-Dsbt.boot.directory=|
|-sbt-dir|-Dsbt.global.base=|
|-sbt-ivy|-Dsbt.ivy.home|
|-debug-inc|-Dxsbt.inc.debug=true|
||-Dsbt.override.build.repos=true|
||-Dsbt.repository.config=$user_home/.sbt/repositories|


### SBT TEST

```bash  
#!/bin/bash
rm -rf /root/.sbt
rm -rf /root/.ivy2
JAVA_HOME="/opt/scala/jdk1.8.0_161"
SCALA_HOME="/opt/scala/scala-2.12.8"
SBT_HOME="/opt/scala/sbt"
# SBT_OPTS=
PATH=$PATH:$JAVA_HOME/bin:$SCALA_HOME/bin:$SBT_HOME/bin
SBT_OPTS=" -Dsbt.global.base=/opt/scala/sbt-home/.sbt/ -Dsbt.boot.directory=/opt/scala/sbt-home/.sbt/boot -Dsbt.ivy.home=/opt/scala/sbt-home/.ivy2/ -Dsbt.override.build.repos=true -Dsbt.repository.config=/opt/scala/sbt-home/.sbt/repositories"
echo "##################################  PATH:  #####################################"
echo $PATH
echo "##################################  SCALA  #####################################"
scala -version
scala -help
echo "###################################  SBT  ######################################"
sbt -v info // env adds $SBT_OPTS
sbt -v debug // env adds $SBT_OPTS
echo "###################################  END  ######################################"
```  
