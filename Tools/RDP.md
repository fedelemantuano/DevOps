# RDP 

Remote Descktop Protocol  

## Windows RDP Client

to manage credentials renewal add the following to a session file (*.rdp) and reload it:
    
    enablecredsspsupport:i:0
    
## Send Ctrl+Alt+Del inside RDP session

<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Canc</kbd> or <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Del</kbd> 
becomes   <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>End</kbd> inside the RDP session
