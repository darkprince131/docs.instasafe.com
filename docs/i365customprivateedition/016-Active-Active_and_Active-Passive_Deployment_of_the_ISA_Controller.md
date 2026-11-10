---
comments: true
---
# Active-Active and Active-Passive Deployment of the ISA Controller

**Active and Passive Modes**

**Active Mode** - When the Controller status is Running, the Controller is in active mode. In this state, the controller is actively performing its designated functions, tasks, or processes, and it is ready to receive and respond to input, commands, or requests. This status indicates that the Controller is actively engaged in its role and is available for its intended purposes.

**Passive Mode** - When the Controller status is Stopped, the Controller is in passive mode. In this state, the Controller is not actively performing its designated functions, tasks, or processes. It is temporarily inactive, not responsive to input, commands, or requests, and is essentially on standby or in a state of rest. The Stopped status implies that the Controller is not actively engaged in its role at that moment, and is not currently available for its intended purposes.

**Active-Passive Deployment**

In deployments demanding high availability for all critical systems, ISA can be configured in Active-Passive mode to ensure redundancy. In such setups, multiple Controllers are deployed across distinct cloud servers, each configured with identical network sizes and port numbers.

For example, when an active Controller is deployed in Cloud Server A with a 10.10.0.0/16 network and listening on UDP port 1355, a passive Controller is simultaneously deployed in Cloud Server B with the same 10.10.0.0/16 network and listening on UDP port 1355. In the event that Cloud Server A needs to be shut down, the Controller in Cloud Server B can be manually activated, providing a manual active-passive deployment mechanism. When Cloud Server A is shut down, users connected to the Controller deployed therein will be disconnected and must be reconnected to the new Controller in Cloud Server B. 

**Active-Active Deployment** 

In deployments where the user count exceeds 1000, a strategy of deploying multiple Controllers is employed to effectively distribute the load. For instance, if there are 5000 users, five Controllers are deployed to ensure optimal performance and efficient resource utilization.



