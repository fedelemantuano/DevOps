# WinRM

## Connect to WinRM server
  
    # Define clear text string for username and password
    [string]$userName = '<username>'
    [string]$userPassword = '<password>'
    # Convert to SecureString
    [securestring]$secStringPassword = ConvertTo-SecureString $userPassword -AsPlainText -Force
    [pscredential]$credObject = New-Object System.Management.Automation.PSCredential ($userName, $secStringPassword)
    # Session option to skip check SSL
    $so = New-WSManSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck

    Connect-WSMan -ConnectionURI https://<host-fqdn>:5986/wsman -Credential $credObject -SessionOption $so
