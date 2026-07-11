# week1

## Initial
```
curl -sfL https://get.k3s.io | sh -

curl -s https://fluxcd.io/install.sh | bash

echo "export KUBECONFIG=/etc/rancher/k3s/k3s.yaml" >> ~/.bashrc 
echo "alias k=kubectl" >> ~/.bashrc

wget https://github.com/derailed/k9s/releases/download/v0.51.0/k9s_linux_amd64.deb

sudo dpkg -i k9s_linux_amd64.deb

```

## go go

```
echo $KUBECONFIG

flux bootstrap github \
  --owner=devops202607 \
  --repository=week1 \
  --branch=main \
  --path=./flux \
  --token-auth
```

```
git clone https://github.com/devops202607/week1.git


k apply -f flux/gitrepository.yaml
k apply -f flux/kustomization.yaml

k apply -f k3s/deployment.yaml

# checking
k get pods
k get ingress
```
