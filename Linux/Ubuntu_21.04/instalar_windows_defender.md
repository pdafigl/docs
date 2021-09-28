# Pasos para instalar Windows Defender en Ubuntu 21.04

Se instalan una serie de librerías necesarias para instalar los repositorios específicos:

```bash
sudo apt install -y curl libplist-utils
```
Se habilitan los repositorios de Microsoft para Ubuntu 21.04:

```bash
sudo curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/21.04/prod.list
sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
sudo apt install gpg
sudo curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
sudo apt install apt-transport-https
sudo apt update
```

Y por último, se instala Windows Defender

```bash
sudo apt -y install mdatp
```

Si lanzamos el comando mdatp podemos ver el menú completo de opciones que nos ofrece este anti-virus en Linux.

[mdatp](images/mdatp.png)