#### Instalación de Kubectl
Esta herramienta nos permitirá gestionar minikube a través de la línea de comando. Para instalarlo:
- Nos descargamos la última versión de kubectl;

```bash
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
```
- Le damos permisos de ejecución:

```bash
sudo chmod +x ./kubectl
```
- Por último, movemos el binario dentro de PATH

```bash
sudo mv kubectl /usr/local/bin/kubectl
```

Podemos comprobar que está instalado correctamente con el siguiente comando:

```bash
kubectl version --client
```