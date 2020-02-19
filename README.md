ws-tcp-bridge
=============

Project status:
 currently not in use  so i dont know if its up to date with its dependencies. Feel free to use the code as an example however
 the only licensing restriction is let me know if its been helpful! 

A websocket to tcp proxy server, using nodejs which bridges websockets and tcp servers in either direction.

WIP - the actual code is extremely simple, but not tested well (YET), feel free to help.
	  working examples will be provided with some real services when I get time. 
*NOTE* - currently I only support binary ws frames which isnt implemented in alot of browsers...
A workaround is simple to implement.


## Install

Install to current directory:

```
 npm install ws-tcp-bridge
./node_modules/.bin/ws-tcp-bridge
```

Install globally

```
npm install -g ws-tcp-bridge
ws-tcp-bridge
```

## Example -

```
$ ws-tcp-bridge --method=ws2tcp --lport=8080  --rhost=127.0.0.1:8081

proxy mode ws -> tcp
forwarding port 8080 to 127.0.0.1:8081
```

```
$ ws-tcp-bridge --method=tcp2ws --lport=8080  --rhost=ws://127.0.0.1:8081

proxy mode tcp -> ws
forwarding port 8080 to 127.0.0.1:8081
```

**To use certificate just pass the key and certificate, message tell that it is active:**

```
$ ws-tcp-bridge --method=ws2tcp --lport=8080  --rhost=127.0.0.1:8081 --key=key.pem --cert=cert.pem

proxy mode ws -> tcp
forwarding port 8080 to 127.0.0.1:8081
Starting secure websocket server
```

Insecure flag is optional to indicate the use of self-signed certificate.

```
$ ws-tcp-bridge --method=tcp2ws --lport=8080  --rhost=ws://127.0.0.1:8081 --insecure

proxy mode tcp -> ws
forwarding port 8080 to 127.0.0.1:8081
```

### Aditional information

To generate a self-signed certificate you can use:

```
$ openssl genrsa -out key.pem 2048
$ openssl req -new -sha256 -key key.pem -out csr.pem
$ openssl x509 -req -in csr.pem -signkey key.pem -out cert.pem
```

If you want to have negotiation of the target address consider forwarding to a socks5 proxy
