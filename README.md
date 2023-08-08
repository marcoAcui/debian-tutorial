## Requisitos:

- [Debian 12 versión netinst.iso](https://www.debian.org/CD/netinst/) (ocupa internet para la instalación)
- 1 servidor con Mouse, Teclado, Monitor conectados y funcionales (tutorial realizado en maquina virtual)
- 1 conexión a internet
- [Esta pagina para la instalación de Apache, MariaDB y PHP](https://wiki.debian.org/LaMp)
- [BD de Acuicultec para la importación desde phpMyAdmin ](https://github.com/ACUICULTEC-S-A-DE-C-V/BD_Software)

Validaciónes para cambios

- requerira superusuario o con el usuario principal bastara?
- Opcion grafica o normal (las opciones no cambian realmente)
- Nombre de maquina
- Selección de Ubicación y Zona Horaria
- Selección de entorno grafico (podria elegirse un DE mas liviano como XCFE o no utilizar ningun entorno grafico por el afan de no utilizar recursos, incluso quitar la personalización de debian y solo instalar lo requerido)
- Mantener y clonar los archivos desde un git privado para la configuración (esto seria si tratamos de configurar un servidor sin interfaz grafica) de otra manera, solo compartiendo con una USB es posible
- Servicios de ubicación - privacidad SI O NO?
- Por default linux y debian son sistemas ligeros pero se puede remover software (la instalacion por default solo pesa 8-9GB y usa 2GB de ram)
- Deshabilitar el login remoto probablemente lo deshabilita para conexiones ssh pero NO para anydesk

# Tutorial de configuración e instalación de un servidor con Linux y Debian 12

### Instalación de Sistema Operativo

Para moverte usar **flechas direccionales** en el teclado o la tecla **TAB**, para elegir es usar **ENTER**, la tecla de **ESPACIO** se utilizará en ciertas ocasiones

1. Ingresar USB a computadora y Bootear en USB

2. Elegir Opción 2 **"Install"** (las opciones en adelante tendrian que ser las mismas si se elige Graphical Install)
   ![Menu inicial](/images/image.png)

3. Seleccionar Lenguaje **Spanish - Español**
   ![Elije un lenguaje](/images/image-1.png)

4. Ubicación: **México** (En caso que sea un servidor para Ecuador seleccionar **Ecuador**)
   ![Ubicación](/images/image-2.png)

5. Configuración de Teclado: **Latinoamericano**
   ![Teclado](/images/image-3.png)

Se hara la configuración de red de manera automatica si se tiene una conexión a internet

6. Ingresar nombre de maquina: **debian** (posible cambio?)
   ![Nombre de Equipo](/images/image-4.png)

7. Nombre de dominio: **dejar en blanco**
   ![Nombre de Dominio](/images/image-5.png)

8. Clave de superusuario: **dejar en blanco** (el usuario que ingresaremos será el superusuario)
   ![COntraseña de Superusuario](/images/image-6.png)

9. Confirmación de contraseña de superusuario: **dejar en blanco**
   ![Confirmación de contraseña de Superusuario](/images/image-7.png)

10. Ingresar Nombre Completo: **SERVIDOR ACUICULTEC**
    ![Nombre Completo](/images/image-8.png)

11. Ingresar nombre de Cuenta: **acuicultec**
    ![Nombre cuenta](/images/image-9.png)

12. Contraseña: **Acuicultec03.** (puede elegirse la opción "Mostrar la contraseña en claro" con la tecla **ESPACIO** si se desea confirmar)
    ![Contraseña](/images/image-10.png)

13. Confirmación de contraseña: **Acuicultec03.** (puede elegirse la opción "Mostrar la contraseña en claro" con la tecla **ESPACIO** si se desea confirmar)
    ![Confirmación contraseña](/images/image-11.png)

14. Selección Zona Horaria: **Pacífico** (En caso que sea un servidor para Ecuador elegir la zona horaria adecuada ya sea **Guayaquil** o **Islas Galápagos**)
    ![Zona Horaria](/images/image-12.png)

15. Partición de Discos: **Particionado guiado**
    ![Partición de discos](/images/image-13.png)

16. Partición de Discos parte2: **Utilizar todo el disco**
    ![Utilizar todo el disco](/images/image-14.png)

17. Partición de Discos parte3 Elegir Disco: **Seleccionar el disco**
    ![Elección de disco](/images/image-15.png)

18. Partición de Discos parte4: **Todos los ficheros en una partición(recomendado para novatos)**
    ![Todos los ficheros en una partición](/images/image-16.png)

19. Partición de Discos parte5: **Finalizar el particionado y escribir los cambios en el disco**
    ![Confirmación de particionado](/images/image-17.png)

20. Partición de Discos parte6: **Elegir Sí**
    ![Confirmación de cambios en disco](/images/image-18.png)

21. Comienza instalación de Sistema **Tomar agua**

22. Configuración de gestor de paquetes, desea analizar medios de instalación adicionales **Elegir NO**
    ![Medios de instalación adicionales](/images/image-19.png)

23. Elegir pais para obtener actualizaciones de Debian **Estados Unidos**
    ![Pais para gestor de paquetes](/images/image-20.png)

24. Elegir URL para replica **deb.debian.org** (esta opción saldrá si se elige Estados Unidos)
    ![URL para gestor de paquetes](/images/image-21.png)

25. Proxy para paquetes **Dejar en Blanco**
    ![Proxy para gestor de paquetes](/images/image-22.png)

26. Enviar anonimamente estadisticas sobre paquetes mas utilizados **como preferencia personal osea de Omar NO pero puede ser cualquier opción**
    ![Estadisticas de paquetes mas utilizados](/images/image-23.png)

27. Selección de Entorno de Escritorio **Presionar TAB para poder elegir la palabra Continuar y darle ENTER** (luego veremos si podemos continuar la configuración sin una interfaz grafica)
    ![Selección de Interfaz Grafica](/images/image-24.png)

28. Sistema seguira instalandose **Tomar mas agua**

29. Configuración de GRUB, si desea instalar el cargador en la unidad principal **Elegir SI**
    ![GRUB](/images/image-25.png)

30. Elegir disco: **/dev/sda** (en la /images/imagen se aprecia VDA por que es un disco virtual)
    ![GRUB pt2](/images/image-26.png)
31. Felicidades Sistema instalado **Darle continuar y remover USB para que proceda el sistema operativo desde el disco duro**
    ![Finalización de instalación](/images/image-27.png)

### Primer Booteo

1. Elegir Opción Debian GNU/Linux **por default se elige sola**
   ![Pantalla de GRUB](/images/image-28.png)

2. Ingresar Contraseña de usuario **Acuicultec03.**

### Configuración Inicial

1. Elegir Español - Mexico
   ![Idioma para configuración inicial](/images/image-29.png)

2. Elegir distribución de teclado **Español (teclas Windows) y Siguiente**
   ![Distribución de teclado](/images/image-30.png)

3. Privacidad, Servicios de ubicación **Activarlo**
   ![Privacidad](/images/image-31.png)

4. Conectar cuentas **Presionar en Omitir**
   ![Omitir](/images/image-32.png)

5. Terminado **Tomar agua y dar click en Empezar a usar Debian GNU/Linux**
   ![Terminado](/images/image-33.png)

6. Dar click derecho en escritorio y **Configuración de pantalla**
   ![Configuración de pantalla](/images/image-34.png)

7. Elegir resolución adeacuada **Caso personal fueron 1920x1080 y Aplicar**
   ![Resolución](/images/image-35.png)

8. Presionar en teclado el boton de Windows (En linux se conoce como la tecla Super) y en el buscador de arriba escribe "Retoques", en el programa que aparecio, dar click en "Barras de titulo de las ventanas" y activar las opciones "Maximizar y Minimizar", cerrar todas las pantallas anteriores
   ![Settings](/images/image-59.png)

9. Presionar en teclado el boton de Windows en dar click en Actividades y dar click en la opcion con 9 puntitos **Mostrar todas las aplicaciones** (tambien se puede usar el buscador y buscar terminal)
   ![Todas las aplicaciones](/images/image-36.png)

10. Elegir Terminal
    ![Terminal](/images/image-37.png)

11. (OPCIONAL) Doble click izquierdo en la barra gris de la terminal para que sea pantalla completa
    ![Terminal](/images/image-38.png)

### Actualización de paquetes

En la terminal:

1. Escribir e ingresar contraseña de usuario cuando se le solicita (la contraseña no se vera, es normal):

```bash
  sudo apt update
  sudo apt upgrade
```

![Update](/images/image-39.png)
![Update listo](/images/image-40.png)

2. Al terminar solo escribir para limpiar la terminal:

```bash
  clear
```

![Upgrade Listo](/images/image-41.png)
![terminal limpia](/images/image-42.png)

### Optimización

Por default Debian no actualiza su software pero podemos remover algunos

1. Dar Click en "Actividades" y Elegir la opcion **Software**
   ![Software](/images/image-43.png)

2. Dar click en la sección de "Instalado" y Remover el siguiente software, si pide contraseña ingresarla en cada situacion (puedes copiar y pegarla)
   ![Software instalado](/images/image-44.png)

- 2048
- Ajedrez
- Cheese
- Cinco o más
- Contactos
- Cuatro en raya
- Evolution
- GNOME Nibbles
- Hitori
- Klotski
- Luces fuera
- Mahjongg
- Minas
- Quadrapassel
- Reversi
- Robots
- Solitario AisleRiot
- Sudoku
- Swell FOop
- Tali
- Taquin
- Tetravex

3. Click derecho en el escritorio y dar click en **"configuración"**, elegir la opción de energia y cambiar Modo de energía a **"Ahorro de energia"** y "Opciones de ahorro de energia" Apagar la pantalla: **Nunca** y Suspender Automaticamente darle click y desactivarlo
   ![Energia](/images/image-49.png)

## Instalar LAMP Stack https://wiki.debian.org/LaMp (puede abrirse en el servidor para copiar codigo cuando es necesario, mantener esta pagina en el proceso)

### Instalar MariaDB (si se desea copiar y pegar comandos, usar Ctrl + Shift + C y Ctrl + SHift + V)

#### Opcional: si no deseas ingresar **sudo** en cada comando que requiera permisos de administrador, puedes escribir "sudo su" y al ingresar la contraseña normal **Acuicultec03.** los comandos de la pagina podran ser facilmente de copiar y pegar; este documento dara por hecho que no realizaste este paso opcional y debes usar sudo cuando se requiera

1. Abrir una terminal y ejecutar el siguiente comando, uno a la vez y darle enter a cada uno:

```bash
  sudo apt update
  sudo apt upgrade
```

2. Abrir una terminal, ejecutar el siguiente comando y confirmar que si se desea instalar:

```bash
  sudo apt install mariadb-server mariadb-client
```

![Instalación MariaDB](/images/image-60.png)

3. Ejecutar el siguiente script:

```bash
  sudo mysql_secure_installation
```

4. Les pedira la contraseña actual de root **darle ENTER por que root no tiene contraseña**
   ![Ingresar contraseña root](/images/image-52.png)

5. EN este paso hace mencion de usar unix_sockets; presionar **N** y **ENTER**

6. En este paso hace mencion de cambiar la contraseña del usuario root de mysql; presionar **S** e indicar la contraseña **1234** confirmarla y **Enter**

   ![Aplicar contraseña 1234](/images/image-69.png)

7. Remover usuarios anonimos **Y** y **ENTER**
   ![Removiendo usuarios anonimos](/images/image-54.png)

8. Deshabilitar login a root remoto **Y** y **ENTER**
   ![Login remoto](/images/image-55.png)

9. Remover base de datos de testing **Y** y **ENTER**
   ![Base de datos testing](/images/image-56.png)

10. Confirmar los cambios **Y** y **ENTER**
    ![Confirmar cambios](/images/image-57.png)

### Instalar apache2

1. Abrir una terminal, ejecutar el siguiente comando y confirmar que si se desea instalar:

```bash
  sudo apt install apache2 apache2-doc
```

![Instalar apache2](/images/image-61.png)

2. Ejecutar el siguiente comando:

```bash
   sudo a2enmod userdir
```

![modulo userdir](/images/image-62.png)

3. Reiniciar el servicio de Apache con este comando:

```bash
   sudo systemctl restart apache2
```

![Reiniciar servicio apache](/images/image-63.png)

4. Ejecutar el siguiente comando el cual abrira un editor de texto en la terminal:

```bash
   sudo nano /etc/apache2/mods-enabled/userdir.conf
```

![nano](/images/image-64.png)

5. Moverte con las flechas de teclado y remover todo el texto con **BACKSPACE**

6. Revisar en el sitio web y copiar el texto que indica **"From apache 2.4 and later use instead:"** con el mouse
   ![Texto Copiado](/images/image-65.png)

7. En el editor de texto/terminal, click derecho y pegar y revisar que sea el mismo texto, despues de confirmar **Ctrl + X**, luego **S** y por ultimo **ENTER**

8. (Opcional) puede volver a revisar el archivo con el comando del paso4 y confirmar que el texto se haya guardado, para salir es con **Ctrl + X**

9. Ejecutar el siguiente comando (no debe ser root o usar sudo):

```bash
   mkdir /home/$USER/public_html
```

![mkdir](/images/image-66.png)

10. Ejecutar el siguiente comando

```bash
   sudo chgrp www-data /home/acuicultec/public_html/
   sudo service apache2 restart
```

![Change group & restart apache](/images/image-67.png)

11. Con esto el servicio de apache2 deberia de estar activo pero se puede revisar con el comando

```bash
   sudo systemctl status apache2
```

![Apache2 Activo](/images/image-48.png)

### Instalar PHP

1. Abrir una terminal, ejecutar el siguiente comando y confirmar que si se desea instalar:

```bash
  sudo apt install php php-mysql
```

2. Crear un archivo de prueba de php con este comando

```bash
   sudo nano /var/www/html/test.php
```

3. Ingresar el siguiente texto, **Ctrl+X** para salir, luego **S** para confirmar y por ultimo **ENTER** para guardar el archivo

```php
  <?php phpinfo();?>
```

4. Confirmar que funciona accediendo a http://localhost/test.php

![PHP](/images/image-68.png)

### Instalar PHPMyAdmin (si se desea copiar y pegar comandos, usar Ctrl + Shift + C)

1. Abrir una terminal y ejecutar el siguiente comando y confirmar que si se desea instalar:

```bash
  sudo apt install phpmyadmin
```

2. Elegir la opcion "apache2" y presionar **ESPACIO" para que seleccione, despues **TAB** y **ENTER\*\* para continuar
   ![instalacion de phpmyadmin](/images/image-58.png)

3. Elegir la opción **SI**

4. Ingresar como contraseña **1234** , **TAB** y **ENTER** para confirmar
5. Mismos pasos para confirmar contraseña
6. Reiniciar apache:

```bash
   sudo /etc/init.d/apache2 restart
```

### Instalar Java y JavaFX

1. Entrar al sitio web https://www.azul.com/downloads/#zulu

2. Navegar en la pagina hasta encontrar la opción para elegir las opciones especificas y elegir acorde
   ![JavaFX](/images/image-70.png)

3. Descargar .deb

4. Entrar a **Archivos** y Buscar en **Descargas**

5. Click Derecho al archivo .deb y dar click en **Abrir Con**
   ![Abrir con](/images/image-71.png)

6. Buscar y elegir la opción **Instalar Software**
   ![Instalar software](/images/image-72.png)

7. Se abrira una nueva ventana en la que solo debemos presionar a instalar
   ![Instalar java](/images/image-73.png)

8. Para confirmar que fue instalado abrir una terminal y escribir el comando **java --version**

```bash
   java --version
```

![Java version](/images/image-74.png)

9. Ejecutar el siguiente comando en terminal

```bash
   sudo nano ~/.bashrc
```

10. Dirigirte hasta el final del archivo de texto que se abrió e ingresar el siguiente texto:
    **export JAVA_HOME=/usr**

11. Cerrar el editor y guardar el texto (**Ctrl + X**, despues **S** y por ultimo **Enter**)
