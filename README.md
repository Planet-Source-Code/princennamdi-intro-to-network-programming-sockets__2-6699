<div align="center">

## Intro To Network Programming: Sockets


</div>

### Description

Just a basic intro into socket programming..
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[princennamdi](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/princennamdi.md)
**Level**          |Intermediate
**User Rating**    |4.0 (20 globes from 5 users)
**Compatibility**  |Java \(JDK 1\.1\), Java \(JDK 1\.2\), Java \(JDK 1\.3\), Java \(JDK 1\.4\), Java \(JDK 1\.5\)
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__2-68.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/princennamdi-intro-to-network-programming-sockets__2-6699/archive/master.zip)





### Source Code

im sure you know what an IP address is, and what a port is....
if u havent, check wikipedia.org
a socket is the combination of an IP address and a port.......
eg...50.50.50.50 : 21
a server is anything that provides a service or services...
and each of those services can be accessed through the respective port...
eg
say if my server ip address is 50.50.50.50,
and i run FTP and HTTP and BLAH on port 21, 80, 9090 respectively.....
if john wants to access FTP services on my server,
he has to use <b> 50.50.50.50:21</b> to access it
if he wants HTTP services on my server, he has to use <b> 50.50.50.50:80</b>
 to access it
and if he wants to access BLAH( my special service ),
 he has to use <b> 50.50.50.50:9090</b> to access it.....
this tutorial will show you how to open a BLAH or whateva service on your system
, so anyone can connect and access your program/service......
Note....you can write custom socket services that can run commands,
 much like netcat in fact, every program that requires a network,
uses socket...eg limewire
first, since we are networking, we need to import the network class
<b>
import java.net.*;
</b>
then we need to import the I/O class....ie for sending and recieving data through the socket
NOTE....i wont send or recieve in this tutorial tho...
<b>
import java.io.*;
</b>
then we need to import the Exception class....for handling errors....
<u>note the exception class is still under the java.io.*........
but i specifically imported it again to show you
 the exact class is java.io.IOException; </u>
<b>
import java.io.IOException*;
</b>
now lets write the obvious
<b>
class server{
 public static void main(String[] args) <u>throws IOException</u>{
  System.out.println("Starting socket......Socket started on port 9090")
  ServerSocket s=new ServerSocket(9090);   //i want the service to run on port 9090
  System.out.println("Waiting for connections.....")
  Socket S=s.accept();  //note program pauses here until connection is made
  System.out.println("Connection Established.....")
  //if you want to close the socket use S.close()
  //if you close the socket you can still reopenit again at port 9090,
  //but if you dont close, you have to use another port number...for now, dont close
  //, just be using different port numbers
  }
}
</b>
well thats it...compile and run
you now have a service running on port whatever you choose...
now lets test it.....while the
program is still running, open up a command prompt and type in.
<b>
telnet localhost 9090
</b>
thats it....
we just wrote the server side of the socket.....in the next tutorial, ill show
you how to send and recieve input through the socket( using Buffered Streams )
and then ill show you how to build a simple chat server, using sockets...
note: i stripped down unnecessary declarations and stuffs to make the tutorial easy......
any Questions, email me

