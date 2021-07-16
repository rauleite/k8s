
# Dashboard

## Start and Tunnel

### Local *(Tunnel remote -> local)*
`ssh -L 8001:localhost:8001 -t raul@192.168.2.2 "cd /home/raul/Documents/dev ; exec $SHELL -l"`

### Remote *(Proxy on 8001)*
`kubectl proxy --address='0.0.0.0'`

### Remote *(Starts without browser)*
`minikube dashboard --url`

### Local
`http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/service?namespace=default`

# Launch
`minikube service hello-minikube --url`

