# Mi configuración e instalación de arch

## Instalación
Utilizando la guía de instalación de arch (archinstall) es bastante sencillo:
1. Sistema de ficheros utilizado BTFS
3. Sin grub (Utilizando la opción por defecto)
4. Con controladores 'All Open Source'. Es importante destacar que inicialmente probé con ATI / AMD pero no me ha dado buen rendimiento a pesar de contar con un procesador Intel y una gráfica AMD Radeon Graphics.
5. Con awesome como gestor de ventanas
6. Con NetworManager
7. Con PulseAudio para la gestión de sonido

Resultado de las particiones con BTFS
![image](https://user-images.githubusercontent.com/60443339/164410752-a7e23dfd-9e60-4fab-acf4-880c3dc09332.png)

## Instalación del gestor de inicio de sesión
Una vez terminada la instalación, se ha instalado gdm (gestor de inicio de sesión de gnome) y habilitado el servicio

Instalación
```console
user@hostname:~$ sudo pacman -S gdm
```
Habilitar el servicio
```console
user@hostname:~$ sudo systemctl enable gdm.service
```
De esta forma, al reiniciar (reboot) se nos carga automaticamente el getor de inicio de sesión y podremos acceder a awesomeWM. Antes de terminar el inicio de sesión es posible que tengamos que seleccionar awesome en el boton de ajustes para cargar dicho gestor y no el de gnome por defecto.

## Instalación de paquetes básicos 
Instalamos algunos de los paquetes de utilidad para mi:

```console
user@hostname:~$ sudo pacman -S ranger rofi kitty chromium pavucontrol git htop nvim flameshot code feh ntfs-3g lxappearance qt5ct arc-solid-gtk-theme arc-icon-theme
```

* **Nemo** es un gestor de archivos y ficheros con interfaz gráfica. Alternativa: **Nautilus** evita algunos problemillas ya que está por defecto y es muy parecido a nemo. 
* **Ranger** es un gestor de archivos y ficheros para la CLI.
* **Rofi** es un menú para lanzar los programas instalados (rofi -show drun).
* **Kitty** es un emulador de terminal que utiliza GPU para acelarar las operaciones. Es muy configurable. Alternativa: **Alacritty** está instalado por defecto con awesomewm. 
* **Chromium** es el navegador chrome desarrollado para sistemas Linux.
* **Pavucontrol** es el controlador de PulseAudio para ajustar aspectos de entrada y salida del volumen.
* **Git** no hace falta explicarlo :)
* **Htop** es un gestor de procesos y recursos para la CLI.
* **Neovim** editor para la CLI (la evolución de vim).
* **Flameshot** para realizar capturas y edición de estas.
* **Code** es un editor de textos y código (Visual Studio Code).
* **Feh** para establecer el fondo de pantalla y mostrar imagenes.
* **ntfs-3g** para desmontar usbs y acceder al contenido de estos cuando su sistema de ficheros es ntfs.
* **xbindkeys** para gestionar la funcionalidad de teclas como subir volumen, bajar volumen, mutear, etc. Igual no hace falta si se controla desde el propio rc.lua de awesome. 
* **lxappearance** para gestionar los temas de gran parte de las aplicaciones de Linux 
* **qt5ct** para gestionar los temas de otra gran parte de las aplicaciones de Linux distintas a las que gestiona lxappearance.
* **arc-solid-gtk-theme** tema de arch para aplicaciones que utilizan el tema establecido por lxappearance.
* **arc-icon-theme** iconos de arch para aplicaciones que utilizan el tema establecido por lxappearance.


## Para siguientes secciones de configuración y comandos de interés
* pactl set-sink-volume @DEFAULT_SINK@ +5%
* pactl set-sink-volume @DEFAULT_SINK@ +5%
sudo pacman -S zsh
echo $SHELL
usermod --shell /usr/bin/zsh mpardo
sudo usermod --shell /usr/bin/zsh mpardo





