ws-tcp-bridge
=============

A websocket to tcp proxy server, using nodejs which bridges websockets and tcp servers in either direction.

WIP - the actual code is extremely simple, but not tested well (YET), feel free to help.
	  working examples will be provided with some real services when I get time. 

*NOTE* - currently I only support binary ws frames which isnt implemented in alot of browsers...
A workaround is simple to implement, but will not be done until after christmas 2012.

INSTALL -

nodejs must be installed first before using this server.

#install to current directory
 npm install ws-tcp-bridge
./node_modules/.bin/ws-tcp-bridge

#or install globally
npm install -g ws-tcp-bridge
ws-tcp-bridge

example -

$ ws-tcp-bridge --method=ws2tcp --lport=8080  --rhost=127.0.0.1:8081

proxy mode ws -> tcp
forwarding port 8080 to 127.0.0.1:8081


$ ws-tcp-bridge --method=tcp2ws --lport=8080  --rhost=ws://127.0.0.1:8081

proxy mode tcp -> ws
forwarding port 8080 to 127.0.0.1:8081


If you want to have negotiation of the target address consider forwarding to a socks5 proxy
