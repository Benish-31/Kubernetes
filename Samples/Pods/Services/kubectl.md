ClusterIP, Loadbalancers, Nodeport
cd samples/services
$ k exec nginx-standalone-77d6656d95-655fz -it sh
# apk add curl
create new command prompt
$ k get pod my-nginx-d789779-dpnv -0 yaml
get back to the previous command prompt
curl http://10.1.0.147 // podIp

open clusterIP.service.yml and this service can only be accessed with the ClusterIP

$ k apply -f clusterip.service.yml
$ k get services

$ go back to the other terminal 

# curl http://10.99.22.129:8080
# curl http://nginx-clusterip:8080 // testing a service on its port

$ k delete service nginx-clusterip

open nodeport.service.yml
$ k apply -f nodeport.service.yml // and this service can be run on localhost:31000
$ k delete service nginx-nodeport

open loadbalancer.service.yml
$ k apply -f loadbalancer.service.yml

