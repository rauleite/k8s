
# Kubernetes

## Proxy 8001

### Local *(Tunnel remote -> local)*
`ssh -L 8001:localhost:8001 -t raul@192.168.2.2 "cd /home/raul/Documents/dev ; exec $SHELL -l"`

### Remote *(Proxy on 8001)*
`kubectl proxy --address='0.0.0.0'`

### Remote *(Starts dashboard without browser)*
`minikube dashboard --url`

### Local
`http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/service?namespace=default`

## Expose a Service
`minikube service hello-minikube --url`

### Local *(Tunnel remote -> local)*
`ssh -L 8080:localhost:8080 -t raul@192.168.2.2 "cd /home/raul/Documents/dev ; exec $SHELL -l"`

### Remote 
`kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080`

## Notion how to install k3os on top of multipass ubuntu
`./k3os-install.sh --takeover --debug --tty ttyS0 --config /tmp/k3os-config.yaml --no-format /dev/vda1 https://github.com/rancher/k3os/releases/download/v0.20.7-k3s1r0/k3os-amd64.iso`

## Multipass with cloud-init *(ssh pub, in this case)*
`multipass launch --name k3s-local --mem 1G --disk 10G --cloud-i
nit=./k3s-config.yaml`
