# nodemigrate

Creates a new K8s node resource based off existing Node resource, copying over the Labels and Spec.Config

## To compile

go build -o nodemigrate main.go

## To use
```
Usage of ./nodemigrate:
  -dst string
    	Name/IP to use for new node (optional)
  -interface string
    	Name of interface to use for k8s
  -ipVersion string
    	IP version to look for (default "4")
  -kubeconfig string
    	(optional) absolute path to the kubeconfig file (default "<HOMEDIR>/.kube/config")
  -src string
    	Name of Source Node to replicate
```

--src and --interface are always required

By default it will find 1st IP on interface to use as nodename. If --dst is set, it will take whatever that is, as precedence. This is in case the interface has multiple IPs configured or you want to use a different nodename than first found IP.


