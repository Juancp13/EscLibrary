---
sidebar_position: 1
---

# Path Hijacking

Consiste en secuestrar un binario del path, cuando se usa un binario como puede ser gzip, si antes de eso se crea otro binario en otra ruta llamado gzip, al ejecutar gzip se
ejecutara primero lo que encuentre en el path, es decir, si el nuevo binario llamado gzip abre una terminal como root, y se encuentra en una ruta quee ejecute antes ese binario 
que el propio gzip, gzip tendra la función que se le ha indicado, no la suya por defecto.


Para que la ubicación del binario "trampa" se ejecute simplemente se añadira la ruta que lo almacena al inicio del path, de la siguiente manera:
```bash
export PATH=<Ubicacioón del binario sustituto>:$PATH
```
