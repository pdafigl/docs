### Pasos para instalar Neofetch

```bash
sudo apt install neofetch
```

### Configurar Banner SSH para ver Neofetch
Se crea un nuevo archivo en la ruta **/etc/update-motd.d**, con el nombre **00-neofetch** (el número inicial marcará la posición en la que apreacerá el banner de neofetch). El contenido de este archivo es:

```bash
#!/bin/bash
printf "\n\n"
neofetch
```
Este archivo se debe crear como root y dar permisos de ejecución a todo usuario:
```bash
chmod +x 00-neofetch
```
La próxima vez que se entre en la máquina a través de SSH, se verá la información que genera Neofetch por defecto.
