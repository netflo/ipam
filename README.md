# ipam

basic non encrypted payload and non https  ... e.g. proof of concept only:

automated IPAM subnet issuance with phpIPAM: 


curl -X POST --user user:pass http://192.168.x.y/api/myappid/user/ -i
==> get the token 

curl -X GET -H 'token: <insert token here>' http://192.168.x.y/api/myappid/sections/1/subnets/ -i
  
issue subnet in an automated fashion with POST or GET to retrieve what it would be:

curl -X GET http://192.168.x.y/api/myappid/subnets/9/first_subnet/25/
section 1 is client 1
subnet 9 is the CIDR to draw subnets from 
/25/ is the subnet size to obtain

curl -X POST to actually book the subnet     curl -X POST http://192.168.x.y/api/myappid/subnets/9/first_subnet/25/

delete with:

typically will need to refresh the token as it will have expired
curl -X DELETE -H 'token: <insert token here>' http://192.168.x.y/api/myappid/subnets/{subnet-id returned from the insert/POST}
  
