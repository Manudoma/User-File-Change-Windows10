# User-File-Change-Windows10
A tutorial to change default disk of users folder to one of your choose.

 - [Español](#Spanish)
 - [English](#English)



## Spanish
Requisitos:
 - Instalador de Windows 10 usb / DVD.
 - Un PC con 2 discos (o dos particiones).
 - Poder formatear dicho PC.
 - 5 minutos mas o menos respecto a una intalación nomal de Windows 10.

### 1. Arrancamos el medio de instalación
Tendremos que arrancar el medio de instalación (ya sea un USB o DVD), como más nos guste hasta llegar a la imagen siguiente:
![](https://img.vim-cn.com/ff/153f41b2744d2f8c8ee7705ba8b61cd27252eb.png)
Aquí pulsaremos ***Ctrl (izquierdo) + Shift/Mayus (Izquierdo) + F3*** y el PC se reiniciara automáticamente en "*Audit Mode*",  con la cuenta de administrador oculta.
![enter image description here](https://img.vim-cn.com/2f/e0076f414bc45e7159302109a459c63b598ede.png)
Este sera el estado de la maquina tras el reinicio.
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

Deberemos de guardar el xml en el disco en el cual vamos a mover las carpetas. 


## English
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzk1ODE4NjgwLC0zMjk3NzE4MjgsMTg1Nz
cyNTQyNyw3MTUwNDA2NTIsLTEzMTgxODkyMDQsODMyNzYzOTc0
LC0xMjk2NTYxNzk1LC0xNDQxNDg5MzU0LDE2NDI3Nzg5OTZdfQ
==
-->