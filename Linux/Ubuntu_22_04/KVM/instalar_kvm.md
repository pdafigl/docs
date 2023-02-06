--- Instalar KVM en Ubuntu 22.04 LTS ---

- Comprobar si está habilitada la virtualización en el equipo:
egrep -c '(vmx|svm)' /proc/cpuinfo

- Comprobar compatibilidad con KVM

apt install cpu-checker
# kvm-ok
INFO: /dev/kvm exists
KVM acceleration can be used

- Se instala KVM
apt install -y qemu-kvm virt-manager libvirt-daemon-system virtinst libvirt-clients bridge-utils

- Se habilita el servicio de virtualización y se arranca:
systemctl enable --now libvirtd
systemctl start libvirtd
