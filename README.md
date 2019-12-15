# User-File-Change-Windows10
A tutorial to change default disk of users folder to one of your choice.

 - [Español](#Spanish)
 - [English](#English)




## Español

<aside class="warning">
No me hago responsable de posibles daños de hardware o software. El usuario utiliza esta guia bajo su propio riesgo.
</aside>

Requisitos:
 - Instalador de Windows 10 usb / DVD.
 - Un PC con 2 discos (o dos particiones).
 - Poder formatear dicho PC.
 - 5 minutos mas o menos respecto a una intalación nomal de Windows 10.

### 1. Arrancamos el medio de instalación
Tendremos que arrancar el medio de instalación (ya sea un USB o DVD), como más nos guste hasta llegar a la imagen siguiente:
![](https://img.vim-cn.com/ff/153f41b2744d2f8c8ee7705ba8b61cd27252eb.png)
Aquí pulsaremos ***Ctrl (izquierdo) + Shift/Mayus (Izquierdo) + F3*** y el PC se reiniciara automáticamente en "*Audit Mode*",  con la cuenta de administrador oculta.
![](https://img.vim-cn.com/2f/e0076f414bc45e7159302109a459c63b598ede.png)
Este sera el estado de la maquina tras el reinicio. Deberemos cancelar la ventana de la imagen.
### 2. Creación de XML
Deberemos crear o descargar (adjunto en el repositorio) un xml llamado *relocate.xml*.
 <details>
  <summary>Creación del XML</summary>
  Abriremos un bloc de notas y pondremos el siguiente contenido:

    <?xml version="1.0" encoding="utf-8"?>
    <unattend xmlns="urn:schemas-microsoft-com:unattend">
    <settings pass="oobeSystem">
    <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <FolderLocations>
    <ProfilesDirectory>D:\Users</ProfilesDirectory>
    </FolderLocations>
    </component>
    </settings>
    </unattend>

Después lo guardaremos como *relocate.xml*. (Asegurarse de que el formato del archivo es XML)
</details>
Una vez tengamos el archivo, por defecto esta configurado para *D:\Users* (No se recomienda cambiar ya que Windows prefiere la letra D como disco secundario). Para cambiarlo necesitaremos editar la linea:

    <ProfilesDirectory>D:\Users</ProfilesDirectory>

Deberemos de guardar el xml en el disco en el cual vamos a mover las carpetas. (ha de ser en el directorio raíz).
### 3. Ejecución del archivo
Abrimos una ventana de cmd como administrador (Win + R) y escribimos:

    %windir%\system32\sysprep\sysprep.exe /oobe /reboot /unattend:d:\relocate.xml

Esto abrirá una ventana similar a esta:

![](https://img.vim-cn.com/e8/7b2c3609c6c553806b6d80af02ef98285ead6c.png)

Despues de esta ventana se nos reiniciara el equipo para proseguir con el proceso normal de instalación de windows. (Tarda un poco mas de lo normal, paciencia)


## English

Requisites:
 - Windows 10 boostable USB or DVD
 - PC with 2 dicks (or two partitions).
 - Make sure you are ready to format this PC.
 - This will take 5 minutes more than a normal Windows instalation.

### 1. Start bootable USB.
Boot de USB or DVD and go on through steps till you see this image:
![](https://img.vim-cn.com/04/364e0e22d993997aa0a9c170f5dc9dbc2c9a5d.png)
Here press ***Ctrl (Left) + Shift (Left) + F3*** and the PC will reboot in "*Audit Mode*",  with the hidden admin account.
![enter image description here](https://img.vim-cn.com/1b/f19e8c09d5471b5f3859d38201a175df63f2e3.png)
After boot we need to cancel this window.
### 2. XML creation
Create or donload a xml file named *relocate.xml*. (Check repository files for download)
 <details>
  <summary>Manual XML creation</summary>
  Open notepad and write/paste this:

    <?xml version="1.0" encoding="utf-8"?>
    <unattend xmlns="urn:schemas-microsoft-com:unattend">
    <settings pass="oobeSystem">
    <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <FolderLocations>
    <ProfilesDirectory>D:\Users</ProfilesDirectory>
    </FolderLocations>
    </component>
    </settings>
    </unattend>

Save it as: *relocate.xml*. (Make sure to save as XML)
</details>
The file its default to folder *D:\Users* (I dont recomend changing it because windows preferse letter D: as second drive). To change directory we need to change:

    <ProfilesDirectory>D:\Users</ProfilesDirectory>

Save/Move the file to de new disk root directory.

### 3. File run
Open a CMD window (from WIN + R) and type:

    %windir%\system32\sysprep\sysprep.exe /oobe /reboot /unattend:d:\relocate.xml

Will see a window looking like this:

![](https://img.vim-cn.com/e8/7b2c3609c6c553806b6d80af02ef98285ead6c.png)

After this window the system will reboot (takes som time) and continue windows normal setup.

That's it, easy right?




<!--stackedit_data:
eyJoaXN0b3J5IjpbNzIzNTUzOTcsLTExNzMzODQ5MDgsLTcxOD
UxMzIyOSwtMzI5NzcxODI4LDE4NTc3MjU0MjcsNzE1MDQwNjUy
LC0xMzE4MTg5MjA0LDgzMjc2Mzk3NCwtMTI5NjU2MTc5NSwtMT
Q0MTQ4OTM1NCwxNjQyNzc4OTk2XX0=
-->