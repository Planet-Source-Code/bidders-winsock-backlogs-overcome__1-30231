<div align="center">

## Winsock backlogs overcome\.\.\.


</div>

### Description

Have you ever written an application that utilises Microsoft's Winsock control? have you ever found that when you tried to send data to a socket, that data becomes compounded with other data sent at a similar time, instead of in a separate transmission? Also applies to those who write multiple connection servers. Read on.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Bidders](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bidders.md)
**Level**          |Beginner
**User Rating**    |4.4 (31 globes from 7 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Internet/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-html__1-34.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bidders-winsock-backlogs-overcome__1-30231/archive/master.zip)





### Source Code

```
This may seem really obvious to you, but myself and George, co-authors of Chapp, have both had immense problems with compounded messages, and messages that would seemingly never send. The situation in which this may be of use is where you have a control-array of winsocks acting as distribution channels for some kind of server. say you wanted to distribute a piece of data to each of the socks. looping through the array and sending to each that had a suitable connection state (7) seems the best way. the problem comes when VB sends the first message and queues the rest... but why?! i've been unable to find any documentation related to this on PSC or on MSDN etc... we've spent months trying to overcome it. and we finally have. Slap a DoEvents on the line before your call to the sockets' senddata function. that's it...
for x=0 to 9
DoEvents
Winsock1(x).senddata "bootittyrah"
next x
Without the doevents, the app wouldn't actually send the other bits of data, until the project is paused and resumed... Strange, but true. at least it was for us. Sorry for the long-windedness... we felt it was justified, based on the time we spent figuring this out. oh, and plz, let's not do the dissing thing? :)
```

