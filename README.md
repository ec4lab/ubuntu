# Ubuntu 24.04

Esta es mi experiencia instalando y usando ubuntu, lo uso de manera múy básica, si tienes alguna sugerencia o aplicación que consideras que este documento debería tener no dudes en [contactarme](ec4lab@gmail.com)

# Instalación

Si vienes de windows, mi recomendación es que no lo reemplaces, puedes realizar una instalación junto a windows.

## Descarga la imagen
Descargar la imagen ISO de la web de [Ubuntu](https://ubuntu.com/download/desktop), yo prefiero 0.4LTS, tienen más soporte,pero si quieres puedes probar otras.  
También existen diferentes [Flavors(https://ubuntu.com/desktop/flavors), que sobre la misma base de ubuntu tienen herramientas adicionales o diferentes entornos de escritorio según necesites.
Si es la primera vez, te recomiendo iniciar con el ubuntu clásico y luego, si quieres, vas experimentando las demás.

## Crear un disco de arranque:
Existes varias herramientas, lo mejor actualmente es ventoy, ya que permite tener un usb con varias imágenes ISO y aún poder utilizarlo para información.
### Instalar ventoy en un usb
Descargar [ventoy](https://sourceforge.net/projects/ventoy/files/v1.1.07/)  
Crear un [usb ventoy](https://www.ventoy.net/en/doc_start.html)
Copia la imagen descargada dentro del USB ventoy


## Instalar Ubuntu
Con la imagen dentro del usb ventoy, reinicia la pc y asegúrate que bootee desde el usb, esto cambia para cada máquina deberás googlear para la tuya en particular, en algunas es presionando `F8` o `F10` o ingresando directamente al menú de la bios con `supr` o `F2` y cambiando el orden de prioridades del booteo.

## Durante la instalación
Sigue las pantallas y coloca tus preferencias, como usuario, nombre del equipo y contraseña,uso horario, idioma de la instalación y teclado.  

En un momento te va a consultar si quieres borrar todo el disco o instalarlo junto a windows, yo uso esa opción. ahi puedes decidir que espacio dejas a windows y a ubuntu.  

Hay opciones avanzadas con la posibilidad de modificar y crear nuevas particiones, si no sabes lo que estás haciendo te recomiendo no jugar con esa sección.  

Por último para no tener problemas de compatibilidad te aconsejo:
* Instalar version completa.
* Con software y driver de terceros.

## Cambiar el tamaño de particiones.

Si te equivocaste en los tamaños o quieres modificarlos, reinicia la pc y bootea nuevamente desde el usb, pero en lugar de seleccionar <kbd>install ubuntu</kbd> selecciona <kbd>Try Ubuntu</kbd>, ya en el escritorio, abre la aplicación `Gparted`y allí puedes modificar los tamaños o incluso eliminar las particiones **MUCHO CUIDADO** esto borra todo archivo y SO que esté en esas particiones

# Personalizar Ubuntu
En Construcción



# Instalar aplicaciones
Existen muchas maneras de instalar aplicaciones en ubuntu, la mayoría las puedes descargar del `centro de aplicaciones`, otras las podrás descargar como `archivos.deb` e instalarlos o ejecutar directamente `archivos.appimage`

## Instalar VSCode
Puedes instalarla desde la tienda

Sino descargar el `instalador.deb` del [sitio oficial](https://code.visualstudio.com/)

Luego abre un terminal `ctrl`+`alt`+`t` y navega hasta el directorio donde descargaste el instalador

```bash
cd Descargas
```
 o desde el explorador vas a carpeta `Descargas`, das click derecho y abrir en un terminal.
```bash
sudo dpkg -i code_1.xxx.x-xxxxxxxxxx_amd64.deb
#Cambiar el nombre según la versión que descargues
```
### Algunas recomendaciones
Sincroniza con tu cuenta de github, asi cada vez que instales tus preferencias y extensiones te acompañaran.

### Extensiones útiles:
+ Python  
+ Pylance  
+ ESPhome  
+ ESPHome Snippets
+ Code Spell Checker
+ Spanish - Code Spell Checker

### Personalizar `settings.json`
presionar `ctrl`+`shift`+`p`  
escribir `settings`
y click en `Open User Settings (JSON)`  
puedes agregar las opciones que deses, mucho ojo con las comas
