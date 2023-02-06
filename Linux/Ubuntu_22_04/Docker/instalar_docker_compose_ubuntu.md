## Pasos para instalar Docker Compose en Ubuntu 22.04 LTS
Se debe reviar el número de versión que se quiere instalar, para indicarlo en la URL del comando CURL. También se debe revisar la arquitectura del procesador del equipo.

Los pasos:

1. Se debe reviar el número de versión que se quiere instalar, para indicarlo en la URL del comando **CURL**. Se puede revisar en [esta URL](https://github.com/docker/compose/releases)

2. Tras eso, se descarga la versión de Docker Compose que se quiere instalar (se muestra comando para la release v2.15.1):
```bash
sudo cd /opt
sudo curl -SL https://github.com/docker/compose/releases/download/v2.15.1/docker-compose-linux-x86_64 -o docker-compose
```
2. Se añade la clave GPG oficial de Docker:

``` bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

3. Se da permisos de ejecución
```bash
sudo chmod +x docker-compose
```

4. Se mueve el binario para que lo utilice cualquier usuario con permisos sobre Docker, del equipo:
```bash
sudo mv docker-compose /usr/local/bin/
```
