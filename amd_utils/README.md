
```bash
CR=hanoverdevamd1f27c34
TAG=rocm6.2_pytorch2.6_utils:v3
docker build -t $CR.azurecr.io/$TAG .

az acr login -n $CR
docker push $CR.azurecr.io/$TAG 
```
