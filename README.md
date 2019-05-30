# 基础介绍
#什么是Websocket

在Http协议中，客户端与服务器端的通信是靠客户端发起请求，然后服务器端收到请求再进行回应，这个过程中，客户端是主动的，服务器端是被动的。Websocket协议就不一样了，它是基于TCP的一种新的网络协议，它与Http协议不同之处就在于Websocket能实现服务器端主动推送消息到客户端，服务器端与客户端都能发起通信，这一次，服务器端终于也拥有了主动权。

#什么是socket.io

socket.io封装了Websocket以及其他的一些协议，并且实现了Websocket的服务端代码。同时还有很强的兼容性，兼容各种浏览器以及移动设备。有了它，我们能更方便快捷地实现服务器端与客户端之间的实时通讯。

服务器端与客户端通信的基本方法
大家可以看一下 [socket.io](https://socket.io/docs/) 的文档

（1）socket.emit
客户端与服务器端之间发送消息是用emit

例如客户端向服务端发送登录请求
socket.emit('login',{username:uname}) login是自定义的事件，后面是带的参数

（2）socket.on

服务器端要接收客户端发送的login事件，就得对该事件进行监听
socket.on('login',function(data){})在回调函数中进行处理
同理，服务器端也可以向客户端发送事件，只要客户端也对该事件进行监听就行

（3）io.sockets.emit
服务器端向连接的所有客户端发送消息得用io.sockets.emit

（4）socket.broadcast.emit
给除了自己以外的客户端广播消息

