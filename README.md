# iotlab



PING 172.22.75.166 (172.22.75.166) 56(84) bytes of data.
64 bytes from 172.22.75.166: icmp_seq=1 ttl=63 time=35.4 ms
64 bytes from 172.22.75.166: icmp_seq=2 ttl=63 time=6.97 ms
64 bytes from 172.22.75.166: icmp_seq=3 ttl=63 time=2.91 ms
64 bytes from 172.22.75.166: icmp_seq=4 ttl=63 time=7.24 ms
64 bytes from 172.22.75.166: icmp_seq=5 ttl=63 time=12.2 ms
64 bytes from 172.22.75.166: icmp_seq=6 ttl=63 time=329 ms
64 bytes from 172.22.75.166: icmp_seq=7 ttl=63 time=4.22 ms


### EndPoint
a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com



### Start GreenGrass Service
* Navigate to /greengrass/ggc/core
* sudo ./greengrassd start

### Check Greengrass' running status
* ps aux | grep -E 'greengrass.*daemon'

#### Starting the greengrass service is needed to deploy the core from aws

### Publisher
* cd path-to-certs-folder
* python basicDiscovery.py --endpoint a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com --rootCA root-ca-cert.pem --cert e5a3442bc7.cert.pem --key e5a3442bc7.private.key --thingName PublisherG2 --topic 'greengrass/group2' --mode publish --message 'Hello, World! Sent from Publisher'

### Subscriber
* cd path-to-certs-folder
* python basicDiscovery.py --endpoint a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com --rootCA root-ca-cert.pem --cert ad2dc1db49.cert.pem --key ad2dc1db49.private.key --thingName Subscriber1G2 --topic 'greengrass/group2' --mode subscribe

#### Change the script name to distance_discovery.py and run the same commands

2019-04-02 20:13:51,596 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Produced [message] event
2019-04-02 20:13:51,599 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Dispatching [message] event
2019-04-02 20:13:51,600 - AWSIoTPythonSDK.core.protocol.internal.clients - DEBUG - Invoking custom event callback...
Received message on topic greengrass/group2: {"message": "Measured Distance = 9.0 cm\n", "sequence": 35}

2019-04-02 20:13:52,599 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Produced [message] event
2019-04-02 20:13:52,603 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Dispatching [message] event
2019-04-02 20:13:52,604 - AWSIoTPythonSDK.core.protocol.internal.clients - DEBUG - Invoking custom event callback...
Received message on topic greengrass/group2: {"message": "Measured Distance = 7.7 cm\n", "sequence": 36}

2019-04-02 20:13:53,605 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Produced [message] event
2019-04-02 20:13:53,606 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Dispatching [message] event
2019-04-02 20:13:53,607 - AWSIoTPythonSDK.core.protocol.internal.clients - DEBUG - Invoking custom event callback...
Received message on topic greengrass/group2: {"message": "Measured Distance = 6.4 cm\n", "sequence": 37}

#### Remember to run the ultrasonic_distance.py in a different tab


