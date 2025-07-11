## Title: Socket re-use address option should be used in SimpleUdpServer

## Description
Nfs gateway restart can fail because of bind error in `SimpleUdpServer`.  
re-use address option should be used in SimpleUdpServer to so that socket bind can happen when it is in TIME_WAIT state

## Stack Trace:
```
org.jboss.netty.channel.ChannelException: Failed to bind to: 0.0.0.0/0.0.0.0:4242  
    at org.jboss.netty.bootstrap.ConnectionlessBootstrap.bind(ConnectionlessBootstrap.java:204),  
    at org.apache.hadoop.oncrpc.SimpleUdpServer.run(SimpleUdpServer.java:68),  
    at org.apache.hadoop.mount.MountdBase.startUDPServer(MountdBase.java:64),  
    at org.apache.hadoop.mount.MountdBase.start(MountdBase.java:97)
```