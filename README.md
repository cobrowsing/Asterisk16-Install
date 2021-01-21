#Instalacion Asterisk 16

En el siguiente documento se generara una guia de instalacion y configuracion de Asterisk 16 dentro de Ubuntu 20 Server. Se utilizara el modulo **pjsip** y la implementacion del protocolo **webRTC**. 

### Descarga

Podra descargar desde el repositorio oficial la version de asterisk que se desee, de la siguiente manera:

```
$ wget http://downloads.asterisk.org/pub/telephony/asterisk/asterisk-16-current.tar.gz
```

Una vez descargado, desempaquete Asterisk:
```
$ tar -xvf asterisk-16-current.tar.gz
```
Ingresar al directorio y continuar a la siguiente seccion.

---

### Instalacion

Para esta seccion deberemos acceder a los permisos de ROOT. Se recomienda ingresar como ROOT con el comando **su**.

###### Instalar prerequisitos:
```
# contrib/scripts/install_prereq install
```
###### Configure Asterisk:

```
# ./configure --libdir=/usr/lib64 --with-pjproject-bundled
```
###### Menuselect:

```
# make menuselect
```
Dentro del menu, deseleccionar los siguientes puntos:

- *Utilities*: Deseleccionar los 3 primeros.
- *Channel Event Logging*: Deseleccionar todo.
- *Compiler Flags*: Seleccionar **BETTER_BACKTRACES**
- *Sounds Packages*: Cambiar a **WAV**.

###### Instalar

```
#make install
```

###### Configurar Asterisk e iniciar
```
# make config
```
