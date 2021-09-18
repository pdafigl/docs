## Pasos para instalar Docker CE en Ubuntu 21.04 LTS
Todo los mostrado está sacado de la documentación oficial de Docker, se puede ver toda la información en [este enlace](https://docs.docker.com/engine/install/ubuntu/).

Los pasos:

1. Se actualiza el índice de paquetes y se instalan una serie de paquetes necesarios:

```bash
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
2. Se añade la clave GPG oficial de Docker:

``` bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

3. Se habilita la versión estable del respositorio:

```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```

  4. Se instala Docker CE:

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
 ```

 5. Por último, para permitir que usuarios distintos al usuario root, puedan lanzar comandos docker, se debe asignar al grupo **docker** a todos los usuarios que queramos permitir lanzar este tipo de comandos:

 ```bash
 sudo usermod -aG docker usuario
 ```
 Tras este cambio, si el usuarios tiene sesión abierta, debe cerrarla y volver a conectarse para aplicar los cambios en su configuración de grupos.
