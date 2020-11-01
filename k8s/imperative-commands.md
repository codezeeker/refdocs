**Imprative command**

`kubectl <verb> <resource> <flags>`

simple points about YAML help

if its represented as &lt;object&gt; - a map -  more than 1 items under &lt;tab&gt;

&lt;\[\] object&gt; - list of maps - more than 1 map each list item starting with hyphen\[-\]

**alias and autocomplete**

```bash
source <(kubectl completion bash)

alias k=kubectl
complete -F __start_kubectl k
```

**help**

`k create service nodeport --help `

`or `

`k create service nodeport --help`

**pod**

`k run nginx --image=nginx --labels=tiers=db  --dry-run=client -o yaml`

**deployment**

`k create deployment nginx --image=nginx --dry-run=client -o yaml`

should note that deployment doesn't have replicas option, instead it can be deployed and scaled to desired

**scale**

`k scale deploy nginx --replicas=2`

**service**

**expose**

For already deployed items, expose can be used to create service

\-\- for deployment

`k expose deploy nginx --type=NodePort --port=8080 --name=test-service --namespace=marketing`

\-\- for pods

`k expose pod redis --name=redis-service --port=8080 --target-port=80`

\*\*\-\- create pod and expose **

`k run httpd --image=httpd --port=80 --expose --dry-run=client -o yaml`

`k create service nodeport my-ns --tcp=5678:8080 --node-port=300028 --dry-run=client -o yaml`

headless svc - when clusterIP set to none

`k create service clusterup mysvc --clusterip="None" -o yaml --dry-run-client`

**set**

set used to update a deployment/pod with new image

#set-image - to update a pod

**annotate**

**logs**

\*\*edit / --edit \*\*

#review an object before creation - one catch is that we have to edit atleast one time to create or remove --edit flg

`k create service clusterip my-svc --clusterip="None" -o yaml --dry-run=client > /tmp/srv.yaml`

`k create --edit -f /tmp/srv.yaml`

**apply**

**label**

`k label node node01 color=blue`

`k get pods --show-labels`

`k get pods -l env=dev,bu=fin`

`k run nginx --image=nginx -l app=nginx, env=dev`

**explain**

`k explain pod | less`

explain pod.spec part and grep for 'env' and show 10 lines after

`k explain pod.spec --recursive | grep 'env' -A10`

`k explain pod.spec.containers --recursive | grep -i 'volume' -A10`

\*\* Login to to the pod  **

`k exec myapp -- cat /log/app.log`

`k exec -it <your-pod-name>  -n <your-namespace>  -- /bin/sh`

it - interactive terminal

**namespace - set namespace context**

`k create ns mynamespace`

\-\- to get all items in all namespaces

`k get all --all-namespaces`

\-\- to set context to particular namespace

`kubectl config set-context --current --namespace=<insert-namespace-name-here>`

\# Validate it

`kubectl config view --minify | grep namespace:`

* * *

**Commands Summary**

**create objects:**

- run
- expose
- autoscale
- create/apply

**modify objects**

- set
- apply
- edit
- scale
- autoscale
- patch

view objects

- logs
- get
- describe

**delete objects**

- delete