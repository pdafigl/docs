# How-Tos de Skaffold
En este documento se recogen una serie de tutoriales de Skaffold. Aquellos procedimientos más complejos, se recogerán en documentos adicionales.

### Instalación de Skaffold en Ubuntu Server 20.04.
Para probar Skaffold en un entorno local, se debe instalar:
- Docker.
- Minikube
- Kubectl
En caso de utilizarlo en un entorno Productivo, será necesario:
- Docker
- Un registry de imágenes de contenedores.

La instalación de Minikube y Kubectl en Ubuntu Server 20.04, podéis encontrarla aquí [instalar-minikube](https://github.com/pdafigl/docs/blob/main/Kubernetes/minikube/instalar-minikube.md)

Para instalar Skaffold bastará con ejecutar el siguiente comando:

```bash
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-linux-amd64 && \
sudo install skaffold /usr/local/bin/
``` 