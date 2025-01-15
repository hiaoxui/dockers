
```bash
CR=hanoverdevamd1f27c34
TAG=guanghui/rocm6.3.0_pytorch2.5.1_flastattn2.7.2:v1
docker build -t $CR.azurecr.io/$TAG .

az acr login -n $CR
docker push $CR.azurecr.io/$TAG
```
