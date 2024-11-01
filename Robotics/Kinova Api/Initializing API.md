### Required imports
```Python
import sys

import os

  

from kortex_api.TCPTransport import TCPTransport

from kortex_api.RouterClient import RouterClient

from kortex_api.SessionManager import SessionManager

  

from kortex_api.autogen.client_stubs.DeviceConfigClientRpc import DeviceConfigClient

from kortex_api.autogen.client_stubs.BaseClientRpc import BaseClient

  

from kortex_api.autogen.messages import DeviceConfig_pb2, Session_pb2, Base_pb2
```

### Initialization

It is recommended to use the `DeviceConnection` utility class to create the router and then create the services you need.

```Python
def example_api_creation(args): 
   PORT = 10000

  

    # Setup API

    error_callback = lambda kException: print("_________ callback error _________ {}".format(kException))

    transport = TCPTransport()

    router = RouterClient(transport, error_callback)

    transport.connect(args.ip, PORT)

  

    # Create session

    session_info = Session_pb2.CreateSessionInfo()

    session_info.username = args.username

    session_info.password = args.password

    session_info.session_inactivity_timeout = 60000   # (milliseconds)

    session_info.connection_inactivity_timeout = 2000 # (milliseconds)

  

    print("Creating session for communication")

    session_manager = SessionManager(router)

    session_manager.CreateSession(session_info)

    print("Session created")

  

    # Create required services

    device_config = DeviceConfigClient(router)

    base = BaseClient(router)

  

    print(device_config.GetDeviceType())

    print(base.GetArmState())

  

    # Close API session

    session_manager.CloseSession()

  

    # Disconnect from the transport object

    transport.disconnect()
```

- `error_callback` will throw an error every time there is an issue with an asynchronous function inside the API.
- `TCPTransport()` is the object responsible for assembling the messages coming from the API. Manages all high-level commands
- `RouterClient()` is responsible for sending the messages from the API to the actual robot. takes the `transport` and `error_callback` objects as arguments.
- After initializing these objects, we send a connect request to the bot using the `transport` object. Takes `args.ip` (defaults to `192.168.1.10`) and `PORT` as arguments. 
- `DeviceConfigClient` and `BaseClient` create the services that contain the main functions to use when sending commands to the arm.