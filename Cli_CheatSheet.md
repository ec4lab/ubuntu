# Comandos en Ubuntu

Fuentes:  

* <https://www.linuxcommand.org>  
* <https://assets.ubuntu.com/v1/d00791ae-ubuntu_cli_cheat_sheet_2025.pdf>

Listado de algunos comandos útiles, para ejecutarlos necesitas abrir un terminal, puedes hacerlo desde el acceso directo en las aplicaciones o con `ctrl`+`alt`+`t`.

Si quieres evitar arrancar desde el directorio personal `/home/usuario/` y tener que navegar con comandos hasta la carpeta donde desees ejecutar el comando o trabajar con algún archivo, puedes navegar desde el explorador `archivos` o `nemo`, luego click derecho -> Abrir en un terminal

>[!TIP]
>Puedes utilizar auto completar escribiendo las primeras letras de un comando o nombre de un archivo y presionar `tab`
>
>Para ejecutar comandos que realizaste hace poco puedes recorrerlos con la flecha hacia arriba.

Para ver todos los comandos que algunas vez ejecutaste

```bash
history
```

Si recuerdas parte de un comando y sabes que ya lo utilizaste, se puede buscar en el historial

```bash
history | grep "PARTE_DEL_COMANDO" # Reemplazar por lo que recuerdes 
```

## Archivos y Directorios

```Bash
clear #Limpiar la pantalla
```

```bash
pwd # Saber en que directorio estás
```

```bash
mkdir CARPETA_NUEVA # Crear una carpeta
```

```bash
rm ARCHIVO.txt # Borrar un archivo
```

```bash
rm -R CARPETA_A_BORRAR # Borrar una carpeta y todo su contenido
```

```bash
touch ARCHIVO #Crea un archivo vacío o actualiza la última fecha de acceso
```

```bash
nano ARCHIVO.txt # Editar un archivo con nano
```

```bash
cat ARCHIVO.txt # Mostrar el contenido de un archivo
```

Ver los archivos y carpetas que hay en el directorio donde estás

```bash
ls # Diferentes colores para carpetas o archivos
ls -a # Muestra también los archivos y carpetas ocultos
ls -a -n # Los muestra como una tabla, y los permisos de escritura y lectura
ls -R # Archivos y carpetas, recursivo a subdirectorios
```

Navegar entre carpetas

```bash
cd Descargas/ # ingresa a la carpeta descargas
cd .. #vuelve a la carpeta superior
cd / # va a la raíz
cd ~ # carpeta personal (/home/USUARIO/)
```

Mover o Renombrar un archivo

```bash
mv ARCHIVO.txt Documentos/ARCHIVO.txt # mueve ARCHIVO.txt a la carpeta Documentos.
mv ARCHIVO.txt LISTADO.txt # Renombra ARCHIVO.txt como LISTADO.txt
mv ARCHIVO.txt Documentos/LISTADO.txt # mueve ARCHIVO.tx a la carpeta Documentos y lo renombra a LISTADO.txt
mv CARPETA/ home/USUARIO/Descargas/ # Resultado: Descargas/CARPETA/subs
```

## Búsqueda

```bash
find /CARPETA_DONDE_BUSCAR -name "NOMBRE" # Buscar archivo
```

```bash
grep "TEXTO" ARCHIVO_O_CARPETA # Buscar texto dentro de un archivo
```

## Compresión

```bash
tar -czvf CARPETA_COMPRIMIDA.tar.gz CARPETA_ORIGINAL/ #Comprimir una carpeta
```

```bash
tar -czvf ARCHIVO_COMPRIMIDO.tar.gz ARCHIVO_ORIGINAL.txt # Comprimir un archivo
```

```bash
tar -xvf ARCHIVO_COMPRIMIDO.tar.gz #Descomprimir, puede ser .gz/.bz/.xz
```

## Información del sistema

```bash
lsb_release -a # Version de ubuntu instalada
```

```bash
uname -a # Toda la información del sistema
```

```bash
top # Procesos del sistema en tiempo real
```

```bash
htop # Muestra el uso de CPU (discrimina por núcleo) y RAM
```

```bash
df -h # Muestra el uso de todos los discos.
```

```bash
free -m # Muestra memoria RAM usada y libre
```

```bash
date # Fecha y hora
```

## Paquetes y dependencias

```bash
sudo apt update # Actualiza lista de paquetes
```

```bash
sudo apt -s upgrade # Actualiza paquetes actualizables
```

```bash
sudo apt install PAQUETE # Instalar aplicación (de la lista de paquetes)
```

```bash
sudo apt install -f --reinstall PAQUETE # Reinstala aplicación
```

```bash
sudo apt remove PAQUETE # Borra una aplicación
```

```bash
sudo apt purge PAQUETE # Borra una aplicación y sus archivos de configuración
```

```bash
sudo dpkg -i PAQUETE.deb # Instalar un paquete.deb

```

## Permisos y propiedad

Hacer ejecutable un archivo:

```bash
chmod u+x <file> Makes a file executable by its owner.
```

Cambiar la propiedad de un archivo o carpeta:

```bash
sudo chown USUARIO:GRUPO Documentos/ARCHIVO.txt # un solo archivo
sudo chown USUARIO:GRUPO -R Documentos/ # recursivo a todo lo que haya dentro de Documentos
```

Cambiar permisos:

```bash
chmod -R 770 Documentos/ARCHIVO.txt
# Primer dígito: Permisos del administrador
# Segundo dígito: Permisos del usuario
# Tercer dígito: Permisos de terceros
# Niveles de permiso: se determina como la suma de
#       4 (leer)+ 2 (escribir) + 1 (ejecutar), entonces:
#       0 (0+0+0), no tiene permisos
#       1 (0+0+1), puede ejecutar
#       2 (0+2+0), puede escribir
#       3 (0+2+1), puede ejecutar y escribir
#       4 (4+0+0), puede leer
#       5 (4+0+1), puede leer y ejecutar
#       6 (4+2+0), puede leer y escribir
#       7 (4+2+1), puede leer,escribir y ejecutar

```

## Acceso ssh

```bash
ssh usuario@IP_O_DOMINIO # puerto 22
```

```bash
ssh usuario@IP_O_DOMINIO -6254 # puerto especial
```

Copiar una carpeta desde el servidor ssh:

```bash
scp -r usuario@IP_O_DOMINIO:/ruta/remota/carpeta /ruta/local/ #Copia Rápida
```

```bash
rsync -avz --progress usuario@IP_O_DOMINIO:/ruta/remota/carpeta /ruta/local/ # Copia solo cambios
```

```bash
rsync -avz --delete usuario@IP_O_DOMINIO:/ruta/remota/carpeta /ruta/local/ #Espejo, también borra.
```

## Redes y Networking

```bash
sudo systemctl restart NetworkManager.service # Reiniciar red
```

```bash
hostname -I # Muestra IP's (LAN VLAN VPN etc)
```

```bash
ip a #  Muestra todas las direcciones IP asignadas a las interfaces de red del sistema
```

## Unidades conectadas (discos y unidades externas)

```bash
lsblk # Datos crudos
```

```bash
lsblk -o NAME,SIZE,FSTYPE,MOUNTPOINT,LABEL,MODEL,FSUSED,FSAVAIL #tabla con labels
```

```bash
watch -n 1 ls /dev/ttyUSB* /dev/ttyACM* # Detectar en que puerto esta conectado un USB o Microcontrolador, para detener: ctrl+C
```

## Cron jobs y scheduling

```bash
crontab -e # Edita cron jobs para el usuario actual
```

```bash
crontab -l # Lista cron jobs  para el usuario actual
```

```bash
sudo nano /etc/crontab # Editar cron a nivel de administrador (root)
```
