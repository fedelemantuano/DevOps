# Windows Errors (cause there are many)

## UPDATE ERROR

Aggiornamento delle funzionalità a Windows 10, versione 1903 - Errore 0xC1900109  
Aggiornamento delle funzionalità a Windows 10, versione 1903 - Errore 0xc1900130  

    # open cmd as admin and execute:
    # Stop services
    net stop bits
    net stop wuauserv
    net stop appidsvc
    net stop cryptsvc
    # Rename Folders
    ren %systemroot%\SoftwareDistribution SoftwareDistribution.bak
    ren %systemroot%\system32\catroot2 catroot2.bak
    # Restart services
    bit di inizio rete
    net start wuauserv
    net start appidsvc
    net start cryptsvc
    # RESTART WINDOWS AND TRY AGAIN
    
