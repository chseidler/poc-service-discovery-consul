`consul agent -dev` - execute agent in DEV mode
`consul members` - display members of the node
`curl localhost:8500/v1/catalog/nodes` - REST API GET to see the actives nodes
`apk -U add bind-tools` install DIG to access DNS server
`dig @localhost -p 8600 consul01.node.consul` get nodes and ips