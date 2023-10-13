# 4 - Configuracion de la Maquina Virtual

- Iniciaremos la maquina virtual seleccionando `Debian GNU/Linux`.
- Introduciremos la `Contraseña de Encriptacion` que usamos, en mi caso `encrP@ssw0rd`.

![ ](./Screen_Shot_2023-10-05_at_8.02.52_PM.png)

 

- A continuacion introducimos nuestro nombre de usuario, en mi caso `mendiola` y su contraseña `userP@ssw0rd`.

![ ](./Screen_Shot_2023-10-05_at_8.16.02_PM.png)

 

## 4.1 - Instalacion de Sudo y configuracion de grupos y usuarios.

Para la instalacion de sudo primero deberemos estar en el usuario `root`, y usaremos el comando `su` para cambiar de usuario y ponemos la contraseña `P@ssw0rdd1`.

1. Una vez en el usuario `root` deberemos poner el comando `apt install sudo` para instalar los paquetes necesarios.
2. Y para que se apliquen los cambios deberemos reiniciar la maquina virtual, para ello usamos el comando `sudo reboot`.
    
    ![ ](./Screen_Shot_2023-10-05_at_8.41.00_PM.png)
    
     
    
3. Al volver abrir la maquina introducimos de nuevo las contraseñas y entramos de nuevo al usuario `root`. Y ahora para comprobar que se instalo correctamente usaremos el comando `sudo -V` para comprobar la version de instalacion de sudo.
    
    ![ ](./Screen_Shot_2023-10-06_at_1.50.52_PM.png)
    
     
    
4. A continuacion probamos a añadir el usuario que ya tenemos creado con `sudo adduser *USER*` y nos tiene que mostrar que ya esta creado.
    
    Seguidamente añadimos el grupo user42 con `sudo addgroup user42` y agregamos el usuario que tenemos al nuevo grupo con `sudo adduser *User* user42`.
    
    **Que es GID❓** es la abreviatura de `Group ID`, podriamos decir que es su identificador.
    
    🤔 **Se ha creado correctamente el grupo?** Lo cierto es que si ya que no ha habido ningún mensaje de error, aún así podemos comprobar si se ha creado con el comando `getent group nombre_grupo` o también podemos hacer `cat /etc/group` y podremos ver todos los grupos y los usuarios que hay dentro de ellos.
    
    ![ ](./Screen_Shot_2023-10-06_at_1.54.06_PM.png)
    
     
    
5. Una vez los hayamos introducido para checkear que todo se haya hecho correctamente podemos ejecutar el comando `getent group GROUP_NAME`o tambien podemos editar el fichero /etc/group `nano /etc/group` y en los grupos `sudo` y `login42` debera aparecer nuestro usuario.
    
    ![Screen Shot 2023-10-06 at 5.38.00 PM.png](./Screen_Shot_2023-10-06_at_5.38.00_PM.png)
    

## 4.2 - Instalacion y configuracion SSH.

**Que es SSH❓** Es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada.

1. Primero actualizaremos los repositorios que definimos en el archivo `/etc/apt/sources.list` usando `sudo apt update`.
    
    ![ ](./Screen_Shot_2023-10-06_at_5.41.36_PM.png)
    
     
    
2. Ahora instalaremos la herramienta principal para poder tener la conectividad con el protocolo SSH, llamada OpenSSH. Usaremos `sudo apt install openssh-server` y diremos que si queremos empezar la instalacion.
    
    ![ ](./Screen_Shot_2023-10-06_at_5.44.24_PM.png)
    
     
    
3. Para comprobar la instalacion usaremos `sudo service ssh status` y debera estar `activo`.
    
    ![ ](./Screen_Shot_2023-10-06_at_5.45.37_PM.png)
    
     
    
4. Tendremos que modificar algunos ficheros y para eso usaremos `Nano` o el editor que prefieras. Deberemos estar en el usuario root y modificaremos el archivo `/etc/ssh/sshd_config`.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.02.15_PM.png)
    
     
    
5. Ahora veremos el documento con este estilo. Las frases que comienzan con # son comentarios y algunas de esas lineas las cambiaremos.
    
    ![Screen Shot 2023-10-06 at 6.02.38 PM.png](./Screen_Shot_2023-10-06_at_6.02.38_PM.png)
    
    - Primero pasamos de #Port 22 → Port 4242.
    
    ![Screen Shot 2023-10-06 at 6.04.28 PM.png](./Screen_Shot_2023-10-06_at_6.04.28_PM.png)
    
    - Cambiamos #PermitRootLogin prohibit-password -> PermitRootLogin no
    
    ![ ](./Screen_Shot_2023-10-06_at_6.08.24_PM.png)
    
     
    
6. Una vez terminado estas modificaciones guardamos el fichero con `ctrl + x` y salimos del archivo escribiendo `Y` y finalmente apretaremos `Enter`.
7. Ahora modificaremos `/etc/ssh/ssh_config`
    
    ![ ](./Screen_Shot_2023-10-06_at_6.14.28_PM.png)
    
     
    
8. Y volveremos a cambiar de #Port 22 → Port 4242.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.15.46_PM.png)
    
     
    
9. Por ultimo para guardar los cambios deberemos resetear el servicio ssh con el comando `sudo service ssh restart` y cuando se reinicie miraremos el `status` del servicio para ver los cambios de los puertos a 4242.
    
    ![Screen Shot 2023-10-06 at 6.20.12 PM.png](./Screen_Shot_2023-10-06_at_6.20.12_PM.png)
    

## 4.3 - Instalacion y configuracion de UFW.

**Que es [UFW](https://es.wikipedia.org/wiki/Uncomplicated_Firewall)❓** Es un [firewall](https://es.wikipedia.org/wiki/Cortafuegos_(inform%C3%A1tica)) el cual utiliza la línea de comandos para configurar las [iptables](https://es.wikipedia.org/wiki/Iptables) usando un pequeño número de comandos simples.

1. Lo primero de todo deberemos instalar UFW y usaremos el comando `sudo apt install ufw` y confirmaremos la instalacion con una y.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.29.08_PM.png)
    
     
    
2. Lo siguiente que deberemos hacer es habilitarlo usando el comando `sudo ufw enable` y seguido nos debe mostrar un mensaje que nos dice que firewall esta activo.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.30.50_PM.png)
    
     
    
3. Ahora permitiremos la conexiones con el puerto 4242 con el comando `sudo ufw allow 4242`.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.32.39_PM.png)
    
     
    
4. Para terminar miraremos el estado de nuestro firewall para ver si esta todo correctamente configurado con `sudo ufw status`.
    
    ![Screen Shot 2023-10-06 at 6.33.58 PM.png](./Screen_Shot_2023-10-06_at_6.33.58_PM.png)
    

## 4.4 - Configurar contraseña fuerte para sudo.

1. Creamos un fichero donde se almacenara la configuracion de la contraseña. Crearemos el fichero con el comando `touch /etc/sudoers.d/config-sudo`.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.50.35_PM.png)
    
     
    
2. Ahora crearemos el directorio donde cada comando de sudo quedara alamcenado. Usaremos `mkdir /var/log/sudo`.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.51.24_PM.png)
    
     
    
3. Abriremos el fichero que nos hemos creado anteriormente usando el comando `nano /etc/sudoers.d/config-sudo`.
    
    ![ ](./Screen_Shot_2023-10-06_at_6.53.03_PM.png)
    
     
    
4. Para cumplir el subject deberemos añadir los siguientes comandos.
    
    ```c
    Defaults  passwd_tries=3
    Defaults  badpass_message="Mensaje de error personalizado"
    Defaults  logfile="/var/log/sudo/sudo_config"
    Defaults  log_input, log_output
    Defaults  iolog_dir="/var/log/sudo"
    Defaults  requiretty
    Defaults  secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
    ```
    
    ![ ](./Screen_Shot_2023-10-06_at_7.03.58_PM.png)
    
     
    
5. Que hace cada comando y como quedaria.
    
    ![Screen Shot 2023-10-06 at 7.04.34 PM.png](./Screen_Shot_2023-10-06_at_7.04.34_PM.png)
    

## 4.5 - Configuracion de politica de contraseñas fuerte.

1. Editamos el fichero `login.defs`.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.26.28_PM.png)
    
     
    
2. Una vez abierto moddificaremos los siguientes parametros:
    1. PASS_MAX_DAYS 99999 -> PASS_MAX_DAYS 30
    2. PASS_MIN_DAYS 0 -> PASS_MIN_DAYS 2

    ![](./Screen_Shot_2023-10-06_at_7.28.04_PM.png)
        
        
        - PASS_MAX_DAYS: Es el tiempo de expiración de la contraseña. El numero = a días.
        - PASS_MIN_DAYS: Dias mínimos permitidos antes de modificar una contraseña.
        - PASS_WARN_AGE: El usuario recibira un mensaje de aviso indicando que faltan los dias especificados para que expire su contraseña.
        
3. Para seguir con la configuracion deberemo instalar unos paquetes con el comando `sudo apt install libpam-pwquality`.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.32.24_PM.png)
    
     
    
4. Ahora modificaremos un archivo con `nano /etc/pam.d/common-password`.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.34.57_PM.png)
    
     
    
5. Ahora añadiremos todas estas lineas despues de `retry=3`.

![minlen=10 ucredit=-1 dcredit=-1 lcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root](./Screen_Shot_2023-10-06_at_7.37.59_PM.png)

minlen=10 ucredit=-1 dcredit=-1 lcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root

**Que hace cada comando❓**

minlen=10 ➤ La cantidad minima de caracteres que debe contener la contraseña.

ucredit=-1 ➤ Como mínimo debe contener una letra mayúscula. Ponemos el - ya que debe contener como mínimo un caracter, si ponemos + nos referimos a como maximo esos caracteres.

dcredit=-1 ➤ Como mínimo debe contener un digito.

lcredit=-1 ➤ Como mínimo debe contener una letra minúscula.

maxrepeat=3 ➤ No puede tener más de 3 veces seguidas el mismo caracter.

reject_username ➤ No puede contener el nombre del usuario.

difok=7 ➤ Debe tener al menos 7 caracteres que no sean parte de la antigua contraseña.

enforce_for_root ➤ Implementaremos esta política para el usuario root.

## 4.6 - Conectarse via SSH.

1. Deberemos cerrar la maquina virtual y darle a configurar desde VirtualBox.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.43.25_PM.png)
    
     
    
2. Seguido pinchamos sobre `Red` y pinchamos en `Avanzadas` para poder llegar a `Reenvio de puertos`.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.45.54_PM.png)
    
     
    
3. Ahora agregamos una regla de reenvio.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.46.48_PM.png)
    
     
    
4. Y en el puerto anfrition y al invitado le añadimos el puerto 4242.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.47.40_PM.png)
    
     
    
5. Para poder conectarnos a la maquina virtual desde la real deberemos escribir el comando `ssh mendiola@localhost -p 4242` y nos pedira la clave de usuario. Cuando nos salga el login en verde sera que estaremos conectados.
    
    ![ ](./Screen_Shot_2023-10-06_at_7.55.34_PM.png)