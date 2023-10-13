## This file describes the steps to do SSH jump on remote machine

https://stackoverflow.com/questions/62133771/how-to-jump-to-an-ip-address-when-connected-to-a-remote-server-on-vs-code

# Jump box with public IP address
Host jump-box
    HostName <Jump-Box-IP>
    User <Your-Jump-Box-User-Name>
    IdentityFile path/to/.ssh/id_rsa

# Target machine with private IP address
Host target-box
    HostName <IP address of target>
    User <Your-Private-Machine's-User-Name>
    IdentityFile path/to/.ssh/id_rsa
    ProxyCommand ssh -q -W %h:%p jump-box

    
