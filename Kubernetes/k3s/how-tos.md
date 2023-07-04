# Cambiar la IP de escucha del servicio
Para cambiar la IP que se ha marcado como por defecto durante la instalación, y sobre la que se ha creado el certificado del servicio de K3S, se debe hacer:
- Parar el servicio de K3S
```bash
systemctl stop k3s
```
- Una vez parado el servicio, se debe editar el archivo **/etc/systemd/system/k3s.service** para incluir en el comando de ejecución la IP con el parámetro **--bind-address** con la IP que se quiera utilizar:
```bash
ExecStartPre=/bin/sh -xc '! /usr/bin/systemctl is-enabled --quiet nm-cloud-setup.service'
ExecStartPre=-/sbin/modprobe br_netfilter
ExecStartPre=-/sbin/modprobe overlay
ExecStart=/usr/local/bin/k3s \
    server --bind-address 192.168.56.101 \
```
- Se arranca el servicio:
```bash
systemctl start k3s
```
Se puede comprobar el cambio en el archivo **/etc/rancher/k3s/k3s.yaml
```yaml
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJkakNDQVIyZ0F3SUJBZ0lCQURBS0JnZ3Foa2pPUFFRREFqQWpNU0V3SHdZRFZRUUREQmhyTTNNdGMyVnkKZG1WeUxXTmhRREUyT0RnME5qY3hNelF3SGhjTk1qTXdOekEwTVRBek9EVTBXaGNOTXpNd056QXhNVEF6T0RVMApXakFqTVNFd0h3WURWUVFEREJock0zTXRjMlZ5ZG1WeUxXTmhRREUyT0RnME5qY3hNelF3V1RBVEJnY3Foa2pPClBRSUJCZ2dxaGtqT1BRTUJCd05DQUFUSXk1bHdYY20wSndQTHhnMDdJSGQvUUtVRkpHMnB6aWR6dXM5cmhQaEoKYkVjUWUvMkFubG5HNndMWnNnajV6SXBodFBRbFQvcW1HL1RtMURDaTZEMHdvMEl3UURBT0JnTlZIUThCQWY4RQpCQU1DQXFRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVVh5RzJBYmp5SjUwakxLZ21xQ09yCmtNWExpK2d3Q2dZSUtvWkl6ajBFQXdJRFJ3QXdSQUlnZTRYNTlpbG9aSnpXRHFwWDZiZC84U0syMU5TYllOTGwKQXU2M2hRb3VYam9DSUFScTA3ZmozbFJKelVLT1M5bUFCSndEbTE4eGFjd1A4MTdiYlhOUytrVDcKLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo=
    server: https://192.168.56.101:6443
  name: default
contexts:
- context:
```
