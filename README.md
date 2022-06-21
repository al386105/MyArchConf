# Mi configuración e instalación de arch

## Instalación
Utilizando la guía de instalación de arch (archinstall) es bastante sencillo:
1. Sistema de ficheros utilizado BTFS
2. Sin grub (Utilizando la opción por defecto)
3. Con controladores 'All Open Source' y en caso de tener tarjeta gráfica de NVIDIA es recomedable usar los controladores propietarios de NVIDIA
4. Con awesome como gestor de ventanas
5. Con NetworManager
6. Con PulseAudio para la gestión de sonido

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
mpardo@arch:~$ sudo pacman -S nemo ranger rofi chromium pavucontrol git htop flameshot code ntfs-3g lxappearance qt5ct arc-solid-gtk-theme arc-icon-theme
```

* **Nemo** es un gestor de archivos y ficheros con interfaz gráfica. Alternativa: **Nautilus**. 
* **Ranger** es un gestor de archivos y ficheros para la CLI.
* **Rofi** es un menú para lanzar los programas instalados (rofi -show drun).
* **Chromium** es el navegador chrome desarrollado para sistemas Linux.
* **Pavucontrol** es el controlador de PulseAudio para ajustar aspectos de entrada y salida del volumen.
* **Git** no hace falta explicarlo :)
* **Htop** es un gestor de procesos y recursos para la CLI.
* **Flameshot** para realizar capturas y edición de estas.
* **Code** es un editor de textos y código (Visual Studio Code).
* **ntfs-3g** para desmontar usbs y acceder al contenido de estos cuando su sistema de ficheros es ntfs.
* **lxappearance** para gestionar los temas de gran parte de las aplicaciones de Linux 
* **qt5ct** para gestionar los temas de otra gran parte de las aplicaciones de Linux distintas a las que gestiona lxappearance.
* **arc-solid-gtk-theme** tema de arch para aplicaciones que utilizan el tema establecido por lxappearance.
* **arc-icon-theme** iconos de arch para aplicaciones que utilizan el tema establecido por lxappearance.

Otros paquetes que normalmente ya están instalados con awesome y que también son de gran utilidad:
* **Alacritty** es un emulador de terminal que utiliza GPU para acelarar las operaciones. Es muy configurable. Alternativa: **Kitty**.
* **Neovim** editor para la CLI (la evolución de vim).
* **Feh** para establecer el fondo de pantalla y mostrar imagenes. 
* **arandr** interfaz sencilla para la gestión de monitores (en caso de que utilices más de un monitor)

Paqutes adicionales
* **Neofetch** te muestra la configuración básica del pc en la terminal. Configurable y visualmente atractivo.
* **lsd** ls mucho más visual (es el ls con esteroides)
* **bat** es el cat mucho más visual (cat con esteroides)
* **picom** permite añadir transparencia por ejemplo en las terminales. 


## Creación de los directorios básicos
```console
mpardo@arch:~$ mkdir Tmp Documents Downloads Desktop Pictures Pictures/Wallpapers
```

## Instalación de hacknerd fonts (me gusta la letra para las terminales):

La descarga se realiza desde la página de hacknerd fonts: https://www.nerdfonts.com/
Lo que hacemos es movernos a la carptea de las fuentes, movemos el zip que nos hemos descargado, lo descomprimimos y ahí se ponen automáticamente las fuentes. Después elimianmos el zip.

```console
mpardo@arch:~$ cd /usr/share/fonts/
mpardo@arch:~$ sudo mv /home/mpardo/Downloads/Hack.zip . 
mpardo@arch:~$ sudo unzip Hack.zip
mpardo@arch:~$ sudo rm Hack.zip
```

## Instalación de zsh y asiganción como shell al usuario:

Opción A:

```console
mpardo@arch:~$ sudo pacman -S zsh
mpardo@arch:~$ sudo usermod --shell /usr/bin/zsh mpardo
```

Opción B

```console
mpardo@arch:~$ sudo pacman -S zsh
mpardo@arch:~$ chsh -s $(which zsh)
```

## Instalación de yay (para la instalación de repos de abiertos y de la comunidad de arch):

```console
mpardo@arch:~$ sudo git clone https://aur.archlinux.org/yay-git.git
mpardo@arch:~$ sudo chown -R mpardo:mpardo ./yay-git
mpardo@arch:~$ cd yay-git
mpardo@arch:~$ makepkg -si
```

## Instalación de snap
```console
mpardo@arch:~$ git clone https://aur.archlinux.org/snapd.git
mpardo@arch:~$ cd snapd
mpardo@arch:~$ makepkg -si
mpardo@arch:~$ sudo systemctl enable --now snapd.socket
mpardo@arch:~$ sudo ln -s /var/lib/snapd/snap /snap
```

![image](https://user-images.githubusercontent.com/60443339/174800803-53a21d17-1f5a-461b-b5cd-cd6e0ac4872c.png)


