#  Instalación de minikube en Ubuntu Server 20.04

## Pasos previos
#### Instalación de VirtualBox tools
Esto solo será necesario en el caso de que estemos trabajando con una máquina virtual en este gestor. Además de que es un paso recomendado en la instalación de todas las máquinas virtuales que corren sobre VirtualBox. Para ello se lanza el siguiente comando:
```bash
sudo apt install virtualbox virtualbox-ext-pack
``` 
#### Instalación de Docker Community edition 
Utilizaremos como driver por defecto a última versión de Docker. Para instalar la versión CE de este motor se hará:



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

