# Description

'k8s-baids' stands for "Kubernetes BASH aids" and it's just a bunch of bash aliases for Kubernetes that grew up and became into a collection of bash functions.

You can use them in a standalone way (just copy/paste functions or aliases to your own files) or you can use it with [baids], a 32 LOC project to sort and manage bash functions and aliases.

# Installation

Just clone or link this project under '~/.baids/functions.d' and reload aliases:

```
git clone https://github.com/rcmorano/k8s-baids.git ~/.baids/functions.d/k8s-baids
baids-reload
```

# Usage

Here is the current almost complete functions list provided. Some are irrelevant/internal, so were removed from the list. 
Although most are self explanatory, some of them provide a full documentation in [docs], some provide arguments check and usage, and some don't provide nothing yet... So please feel free to contribute :D!

```
k3s-install
k3s-install-docker-compose
k3s-install-systemd
k3s-uninstall
k8sb-get-dashboard-service
k8sb-install-k8s-dashboard
k8sb-uninstall-k8s-dashboard
kompose-get-latest-tag
kompose-install
kompose-set-version
kompose-uninstall
kompose-upgrade-to-latest-version
kubectl-create-admin-user
kubectl-delete-related-resource-on-namespace
kubectl-get-all-namespaces-names
kubectl-get-all-resources-summary
kubectl-get-all-resources-summary-for-ns
kubectl-get-all-running-pods
kubectl-get-all-services
kubectl-get-namespaced-resources
kubectl-get-nodes-external-ips
kubectl-get-nodes-internal-ips
kubectl-get-not-namespaced-resources
kubectl-get-user-token
skaffold-get-latest-tag
skaffold-install
skaffold-uninstall
skaffold-upgrade
```

You'll basically find two types of files/functions:

* _00-$K8S_PROVIDER_: this 00-priority files provide functions for installing, removing and managing k8s-related tools such as [k3s], [skaffold] or [kompose].
* _10-$K8S_TOOL_: this 10-priority files provide functions for interacting with a k8s cluster with tools like [kubectl], [skaffold]...

# Extending/Contributing

1. Fork project
2. Add some bash functions (in e.g. your custom 'docker run' for exposing port 80 for a determined project)
3. Execute 'baids-remap' and get shortened aliases for your functions
4. Commit your changes
5. Optionally, if you consider that your functions are generic enough to help someone out there, send me a pull request! 

An easy way to contribute could be to write documentation for some of the baids. This can be done by writing [tomdoc](http://tomdoc.org/) right before the function definition and then, updating the markdown templates by executing:

```
k8sb-generate-doc
```

# License and Author                                                             
                                                                                 
Author:: Roberto C. Morano (<rcmova@gmail.com>)                                  
                                                                                 
Copyright:: 2019, Roberto C. Morano (<rcmova@gmail.com>)                         
                                                                                 
Licensed under the Apache License, Version 2.0 (the "License");                  
you may not use this file except in compliance with the License.                 
You may obtain a copy of the License at                                          
                                                                                 
    http://www.apache.org/licenses/LICENSE-2.0                                   
                                                                                 
Unless required by applicable law or agreed to in writing, software              
distributed under the License is distributed on an "AS IS" BASIS,                
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.         
See the License for the specific language governing permissions and              
limitations under the License.

[baids]: https://github.com/rcmorano/baids
[k3s]: https://github.com/rancher/k3s
[kubectl]: https://github.com/kubernetes/kubectl
[kompose]: https://github.com/kubernetes/kompose
[skaffold]: https://github.com/GoogleContainerTools/skaffold
