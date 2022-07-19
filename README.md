# Port-Forward-with-netsh
### Use netsh for Port Forwarding in PowerShell

1.  Check all port proxy that used in localhost with :
    netsh interface portproxy show all

2.  Check Port that you want to use in target [hostname/ip address] as port listener : 
    Test-NetConnection -ComputerName [target hostname/ip address] -Port [port]
    
3.  add net port listener / port forwarding using this code :
    netsh interface portproxy add v4tov4 listenport=[listenerport] listenaddress=[0.0.0.0 as localhost] connectport=[connected port] connectaddress=[connected ip address]

4.  check new port forwarding with this code again :
    netsh interface portproxy show all
    
5.  if you want to delete port listener use this code :
    netsh interface portproxy delete v4tov4 listenport=2901 listenaddress=0.0.0.0

Thankyou
