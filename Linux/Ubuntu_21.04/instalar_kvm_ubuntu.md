## Instalar KVM y virt-manager en Ubuntu 21.04  

- Se comrpueba si el equipo es compatible con la instalación de KVM. Para ello, el valor del siguiente comando debe ser **mayor de 0**.
```bash
egrep -c '(vmx|svm)' /proc/cpuinfo
```
- Instalamos la herramienta de cpu-checker para confirmar que es posible utilizr KVM por configuración del procesador. De no aparecer, se debe habilitar la propiedad de virtualización en el procesador, a través de la BIOS.
```bash
sudo apt install -y cpu-checker
sudo kvm-ok
```
La salida que debemos ver es:
```bash
INFO: /dev/kvm exists
KVM acceleration can be used
```
- Una vez comprobado que es posible instalar KVM, se instalan los siguientes paquetes:
```bash
sudo apt install -y qemu qemu-kvm libvirt-daemon libvirt-clients bridge-utils virt-manager
```

- Comprobamos que el proceso está arriba y se habilita para que arranque con la máquina, si se quiere este comportamiento:
```bash
sudo systemctl status libvirtd
sudo systemctl enable --now libvirtd
```
- Para poder ver el listado de sistemas operativos compoatibles con KVM, instalamos la siguiente herramienta:
```bash
sudo apt install libosinfo-bin
```
Y lanzamos el seiguiente comando para ver el listado de operativos compatibles:
```bash
osinfo-query os
```

