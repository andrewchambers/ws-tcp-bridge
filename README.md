ws-tcp-bridge
=============

A websocket to tcp proxy server, using nodejs which bridges websockets and tcp servers in either direction.


INSTALL -

 npm install ws-tcp-bridge

WIP - the actual code is extremely simple, but not tested well (YET), feel free to help.

*NOTE* - currently I only support binary ws which isnt implemented in alot of browsers...
A workaround is simple to implement, but will not be done until after christmas 2012.

example -

$ ws-tcp-bridge --method=ws2tcp --lport=8080  --rhost=127.0.0.1:8081

proxy mode ws -> tcp
forwarding port 8080 to 127.0.0.1:8081


$ ws-tcp-bridge --method=tcp2ws --lport=8080  --rhost=ws://127.0.0.1:8081

proxy mode tcp -> ws
forwarding port 8080 to 127.0.0.1:8081


If you want to have negotiation of the target address consider forwarding to a socks5 proxy
