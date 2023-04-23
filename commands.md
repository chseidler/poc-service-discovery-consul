`consul agent -dev` - execute agent in DEV mode
`consul members` - display members of the node
`curl localhost:8500/v1/catalog/nodes` - REST API GET to see the actives nodes
`apk -U add bind-tools` install DIG to access DNS server
`dig @localhost -p 8600 consul01.node.consul` get nodes and ips
`ifconfig` to get the ip address
`mkdir /etc/consul.d`
`mkdir /var/lib/consul`
`consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.18.0.2 -data-dir=/var/lib/consul -config-dir=/etc/consul.d` up consul server with configs
`consul join 172.18.0.2` one node connect to another

`consul agent -bind=172.18.0.4 -data-dir=/var/lib/consul -config-dir=/etc/consul.d`

`dig @localhost -p 8600 nginx.service.consul`

`curl localhost:8500/v1/catalog/services`
`curl catalog nodes -service nginx`
`curl catalog nodes -detailed`

`consul agent -bind=172.18.0.4 -data-dir=/var/lib/consul -config-dir=/etc/consul.d -retry-join=bind=172.18.0.2 -retry-join=bind=172.18.0.5` retry-join