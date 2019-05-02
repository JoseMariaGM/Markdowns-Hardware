# Documentación de instalación Debian.

Utilizamos un USB con la ISO de Debian que queramos instalar.

Una vez hayamos entrado en la instalación, empezaremos eligiendo el apartado "Graphical Debian install".

  
![alt text](https://cdn-images-1.medium.com/fit/t/1600/480/1*IA5C_LoxN67FRTcaZXelDQ.png)

La *Lengua* de este será en "English".

![alt text](http://go2linux.garron.me/pics/debian-installer/localechooser_languagelist_0.png)

La *Localización* será Europe, Spain la hora también.

Después de esto, empezará a correr la configuración de red.

A continuación ponemos el usuario y contraseña.
user -> guest
passw -> guest
Superuser -> root
passw -> root

Swap -> Swapoff

Al momento de hacer el particionamiento, si se hace manualmente deberemos utilizar la partición de Debian como "/" (boot).

" # 8  primària  50GB  F ext4    / "

Una vez este configurado de esta manera, utilizaremos "Enter"  en el apartado "Finalizar particionado y escribir los cambios en el disco."

Debian usa **GRUB** , y no **GRUB2** .

# Recuperación GRUB2

Para poder solucionar el problema del grub, deberemos entra meediante una ISO de Fedora 27 para recuperarlo.

Entraremos en la terminal.
mkdir /mnt/disc
mount /dev/sda8 /mnt/disc
grub2-install --boot-directory=/mnt/disc/boot /dev/sda

Una vez hayamos finalizado con este proceso, habrá que añadir la entrada de Debian a nuestro grub.cfg.
