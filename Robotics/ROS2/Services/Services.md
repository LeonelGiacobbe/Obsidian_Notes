---
Status: Not started
Nav2: false
---
Method of communication between nodes in the ROS graph. Services only transport data when they are specifically called by a client (they are synchronous).

How they work:

- the CLIENT calls the service -> Request
- the SERVER provides data -> Response
- the response is given to the CLIENT.  
      
    

![[/Untitled 20.png|Untitled 20.png]]

  
There can be many clients for the same service, but there can only be one server  

## Service Types

  
Services have types that determine how the data returned from that service is structured.  
They have two parts: one for the request (provided by the Client), and another for the response (provided by the Server).  
To find out the type of a service:  

  

- `ros2 service type <service_name>`

## How to call a service

`ros2 service call <service_name> <service_type> <arguments>`  
The  
`<arguments` part is not always needed