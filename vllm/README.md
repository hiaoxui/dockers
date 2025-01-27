```bash
CR=hanoverdevamd1f27c34
TAG=guanghui/vllm:v1
docker build -t $CR.azurecr.io/$TAG .

az acr login -n $CR
docker push $CR.azurecr.io/$TAG

# docker run -it $CR.azurecr.io/$TAG
```
