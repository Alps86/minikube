export KOPS_STATE_STORE=s3://xxxxx-kubernetes-test

kops create cluster \
--cloud=aws \
--master-zones=eu-central-1a,eu-central-1b,eu-central-1c \
--zones=eu-central-1a,eu-central-1b,eu-central-1c \
--node-count=1 \
--topology private \
--networking kopeio-vxlan \
--node-size=t2.micro \
--master-size=t2.micro \
--topology private \
--target=terraform \
--authorization=RBAC \
xxxxx.k8s.local


kops update cluster xxxxx.k8s.local --yes

kubectl get nodes

kops validate cluster


#helm
https://docs.bitnami.com/kubernetes/how-to/configure-rbac-in-your-kubernetes-cluster/

helm install stable/kube2iam --name kube2iam --namespace=kube-system --set host.iptables=true --set rbac.create=true

kops delete cluster --name xxxxx.k8s.local --yes