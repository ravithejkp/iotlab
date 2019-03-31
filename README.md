# iotlab



PING 172.22.75.166 (172.22.75.166) 56(84) bytes of data.
64 bytes from 172.22.75.166: icmp_seq=1 ttl=63 time=35.4 ms
64 bytes from 172.22.75.166: icmp_seq=2 ttl=63 time=6.97 ms
64 bytes from 172.22.75.166: icmp_seq=3 ttl=63 time=2.91 ms
64 bytes from 172.22.75.166: icmp_seq=4 ttl=63 time=7.24 ms
64 bytes from 172.22.75.166: icmp_seq=5 ttl=63 time=12.2 ms
64 bytes from 172.22.75.166: icmp_seq=6 ttl=63 time=329 ms
64 bytes from 172.22.75.166: icmp_seq=7 ttl=63 time=4.22 ms


EndPoint: a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com

Publisher:
cd path-to-certs-folder
python basicDiscovery.py --endpoint a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com --rootCA root-ca-cert.pem --cert e5a3442bc7.cert.pem --key e5a3442bc7.private.key --thingName PublisherG2 --topic 'greengrass/group2' --mode publish --message 'Hello, World! Sent from Publisher'

Subscriber:
cd path-to-certs-folder
python basicDiscovery.py --endpoint a2nwsoqeru0ok9-ats.iot.us-west-2.amazonaws.com --rootCA root-ca-cert.pem --cert ad2dc1db49.cert.pem --key ad2dc1db49.private.key --thingName Subscriber1G2 --topic 'greengrass/group2' --mode subscribe
