---
Status: Not started
Nav2: false
---
Topics are a communication mechanism between [[Nodes]]in ROS2.

  

Some nodes broadcast information (called ‘publishing’), while others  
read that information (called ‘subscribing’). Topics have a unique name,  
allowing for specific and precise communication.  

  

Communication between nodes via topics is asynchronous. Nodes can  
publish messages at their own rate, and subscribers will receive the  
messages whenever they are available.  

  

Topics have a ‘type’, which defines the format of the message that is  
published and received, as well as the kind of information contained  
within it.  

  

Topics allow multiple nodes to publish or subscribe to them.

  

Topics generally are asynchronous, meaning that the message does not  
have to be received at the same time it is published. This differs from  
  
[[Services]], which are synchronous and only work on one-to-one node  
situations.  

Call `ros2 topic info 'nameOfTopic'` to see some basic information about a topic.