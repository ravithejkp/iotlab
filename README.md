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

2019-04-02 20:08:59,358 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Produced [message] event
2019-04-02 20:08:59,360 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Dispatching [message] event
2019-04-02 20:08:59,361 - AWSIoTPythonSDK.core.protocol.internal.clients - DEBUG - Invoking custom event callback...
Received message on topic greengrass/group2: {"message": "Measured Distance = 172.6 cm\n", "sequence": 88}

2019-04-02 20:09:00,362 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Produced [message] event
2019-04-02 20:09:00,365 - AWSIoTPythonSDK.core.protocol.internal.workers - DEBUG - Dispatching [message] event
2019-04-02 20:09:00,366 - AWSIoTPythonSDK.core.protocol.internal.clients - DEBUG - Invoking custom event callback...
Received message on topic greengrass/group2: {"message": "Measured Distance = 172.6 cm\n", "sequence": 89}

