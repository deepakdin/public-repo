## Docker Image
    - https://hub.docker.com/_/mongo
    - https://hub.docker.com/_/mongo-express

## Base64 Encode
https://www.base64encode.org/

admin=>YWRtaW4=
password=>cGFzc3dvcmQ=

username=>dXNlcm5hbWU=
password=>cGFzc3dvcmQ=

## Verify configmap and secret
kubectl get configmap
kubectl describe configmap mongo-configmap

kubectl get secret
kubectl describe configmap mongo-secret

## Access Mongo Express UI
http://<service-lb-ip>>:8081/
http://4.144.57.158:8081/
Provide the web credential: username/password

