---
sidebar_position: 2
---

# Sanitizar terminal

Se indicara somo sanitizar un shell paso a paso mediante el uso de python.

Dentro de la **nueva shell** se eejecutara el comando
```bash
/dev/null -c bash
```
A continuación, se pulsara **Ctrl+Z**, seguidamente se utilizara el comando
```bash
stty raw -echo; fg
```
Se reseteara la terminal mediane el comando reset, una vez hecho esto solicitara un tipo de terminal se le indicara xterm.
Al haber hecho esto se habra iniciado una nueva terminal.

## Poder usar Ctrl+L y otros usos de teclas

Para poder esto se exportara la shell y el term.
```bash
export TERM=xterm
export SHELL=bash
```
## Ajustar tamaño filas y columnas

En la terminal principal se obtendra el tamaño de filas y columnas para adaptarlo a la nueva terminal
```bash
stty size
```
Una vez heecho esto se guardaran los numeros adquiridos y se ejecutaran en la nueva terminal los siguientes comandos.
```bash
stt rows <TusRows> columns <TusColumns>
```

Con esto ya estaría la nueva terminal
