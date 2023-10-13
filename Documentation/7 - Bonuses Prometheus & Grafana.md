# 7 - Bonuses Prometheus & Grafana

Estos bonuses son 3 bonus distintos:

- Primer bonus fueron las particiones al instalar Debian.
- Añade un WordPress funcional con los servicios de: lighttpd, MariaDB, and PHP.
- Agregar un servicio a mi eleccion, usaremos el Prometheus & Grafana.

## 7.2 - WordPress funcional.

### Lighttpd

**Que es Lighttpd❓** Es un servidor web diseñado para ser rápido, seguro, flexible, y fiel a los estándares. Está optimizado y consume menos CPU y memoria RAM que otros servidores.

1. Instalamos los paquetes de lighttpd con `sudo apt install lighttpd`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.15.05_PM.png)
    
     
    
2. Ahora deberems permitir las conexiones mediante el puerto 80 con `sudo ufw allow 80` y confirmamos que  hemos permitido la conexion a dicho puerto 80 con `sudo ufw status`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.21.37_PM.png)
    
     
    
3. Y finalmente añadimos el puerto 80 en los puertos de reenvio. Cerraremos la maquina eh iremos a Configuracion → Red → Reenvio de Puertos → Añadir Puerto 80. Y confirmamos todos los cambios.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.23.50_PM.png)
    
     
    

### WordPress

**Que es Wordpress❓** Es un sistema de gestión de contenidos enfocado a la creación de cualquier tipo de página web y de gestionar todo tipo de contenido con toda la gran cantida de plugins exsistentes.

1. Primero de todo deberemos installar wget y zip para poder gestionar la descarga de archivos y su compresion y descompresion de los mismos con `sudo apt install wget zip`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.28.42_PM.png)
    
     
    
2. Proseguimos accediendo a la carpeta `/var/www` con `cd` y proseguimos instalando la ultima version de WordPress en Español con: `sudo wget https://es.wordpress.org/latest-es_ES.zip`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.48.47_PM.png)
    
     
    
3. Descomprimimos el archivo que acabamos de descargar con `sudo unzip latest-es_ES.zip`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.52.04_PM.png)
    
     
    
4. Ahora renombraremos la carpeta html con `sudo mv html html_old`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.53.29_PM.png)
    
     
    
5. Renombramos la carpeta wordpress a html con `sudo mv wordpress html`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.54.52_PM.png)
    
     
    
6. Y finalmente le damos permisos a la nueva carpeta html de permisos de lectura, escritura y ejecucion al propietario y los grupos y otros con permisos de lectura y ejecucion con el comando `sudo chmod 755 -R html`. 
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_9.57.23_PM.png)
    
     
    

### MariaDB

**Que es MariaDB❓** Es una base de datos. Se utiliza para diversos fines, como el almacenamiento de datos, el comercio electrónico, funciones a nivel empresarial y las aplicaciones de registro.

1. Instalaremos los paquetes de MariaDB con `sudo apt install mariadb-server`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.00.53_PM.png)
    
     
    
2. Para hacer mas segura la instalacion de MariaDB utilizaremos un script que nos proporciona el paquete de mariadb-server con el siguiente comando `sudo mysql_secure_installation`.
    
    Al realizar este comando nos hara una serie de preguntas:
    
    ```c
    Switch to unix_socket autentication? → N
    Change the root password? → N
    Remove anonymous users? → Y
    Disallow root login remotely? → Y
    Remove test database and acces to it? → Y
    Reaload privilege tables now? → Y
    ```
    
    - Switch to unix_socket autentication? Como tenemos una cuenta root protegida no queremos que cambie la autenticacion asique escogemos `N`.
    - Change the root password? Por defecto no tenemos contraseña y no queremos cambiar la contraseña del usuario root asique escogemos `N`.
    - Remove anonymous users? Por defecto cuando instalamos tenemos un usuario anonimo por lo que cualquier persona puede acceder sin cuenta por lo que escogemos `Y`.
    - Disallow root login remotely? Realizaremos esto para que nadie pueda adivinar la contraseña del usuario root ni que accedan como el asique escogemos `Y`.
    - Remove test database and acces to it? Con esto eliminaremos la base de datos y los usuarios de prueba que tengan acceso asique escogemos `Y`.
    - Reaload privilege tables now? Para qie los cambios de la configuracion entren en vigor de inmediato en las tablas de permisos de MYSQL aceptaremos escogiendo `Y`.
    
    ![Screen Shot 2023-10-10 at 10.37.49 PM.png](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.37.49_PM.png)
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.39.13_PM.png)
    
     
    
3. Al teminar este proceso de instalar MariaDB deberemos crear la base de datos y el usuario y lo primero accederemos a mariadb con `mariadb`. Y crearemos la base de datos utilizando el comando `CREATE DATABASE wp_database;`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.45.21_PM.png)
    
     
    
4. Y comprobaremos que se creo correctamente con `SHOW DATABASES;`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.47.21_PM.png)
    
     
    
5. Ahora crearemos un usuario usando `CREATE USER ‘user’@’localhost’ IDENTIFIED BY ‘12345’;`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.50.10_PM.png)
    
     
    
6. Ahora agregaremos el usuario a nuestra base de datos dandole los suficientes permisos para que pueda trabajar con`GRANT ALL PRIVILEGES ON wp_database.* TO ‘user’@’localhost’;`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.53.37_PM.png)
    
     
    
7. Actualizamos los permisos para que los cambios surjan efecto con `FLUSH PRIVILEGES;`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.55.04_PM.png)
    
     
    
8. Una vez finalizado podremos salir de MariaDB con `exit` o `ctrl + z`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_10.56.37_PM.png)
    
     
    

### PHP y Configuracion de WordPress.

**Que es PHP❓** Es un lenguaje de programación. Se utiliza principalmente para desarrollar aplicaciones web dinámicas y sitios web interactivos. PHP se ejecuta en el lado del servidor.

1. Primero instalaremos los paquetes necesarios para poder ejecutar lenguaje PHP y que necesiten conectar a una base de datos MySQL con `sudo apt install php-cgi php-mysql`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.20.45_PM.png)
    
     
    
2. Accedemos al directorio `/var/www/html` con cd. Desde ahi copiaremos el fichero llamado `wp-config-sample.php` como `wp-config.php` con `cp`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_11.05.34_PM.png)
    
     
    
3. Una vez creado modificaremos el archivo con `nano wp-config.php`.
    
    ![Aqui cambiaremos los datos por los nuestros como la siguiente imagen.](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_12.10.33_AM.png)
    
    Aqui cambiaremos los datos por los nuestros como la siguiente imagen.
    
    ![  ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_11.09.58_PM.png)
    
      
    
4. Ahora para mejorar el rendimiento y la velocidad de aplicaciones en el servidor haremos uso de Lighttpd con uno de sus modulos con el comando `sudo lighty-enable-mod fastcgi`. Y tambien mejoraremos eso mismo pero basadas en PHP del servidor con `sudo lighty-enable-mod fastcgi-php`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_11.15.08_PM.png)
    
     
    
5. Y siguiendo a eso como nos dicen forzaremos la recarga del servicio lightpd con `sudo service lighttpd force-reload`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_11.16.47_PM.png)
    
     
    
6. Y si queremos comprobar el estado del servicio usamos `sudo service lighttpd status`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.28.35_PM.png)
    
     
    
7. Una vez completado lo anterior podremos acceder mediante el navegador a nuestro servicio mediante `localhost`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.32.00_PM.png)
    
     
    
8. A continuacion rellenaremos los campos que nos piden, en mi caso terminara de esta forma.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.34.47_PM.png)
    
     
    
9. Una vez dado en `Instalar WordPress` podremos ver la pagina web ya funcional escribiendo [localhost](http://localhost) en nuestro navegador.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.36.22_PM.png)
    
     
    
10. Una vez presionemos `Acceder` o escribamos en el navegador [`localhost/wp-admin`](http://localhost/wp-admin) accederemos al panel de aministracion del sistema WordPress introduciendo nuestro usuario y nuestra contraseña elegida.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.42.00_PM.png)
    
     
    
11. Aqui podremos modificar y personalizar esta pagina web a nuestro gusto pero como no esta nada especificado en nuestro subject no trataremos nada de eso aqui.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_1.43.03_PM.png)
    
     
    

## 7.3 - Download and Install Prometheus.

Utilizaremos una [Guia](https://www.linode.com/docs/guides/how-to-install-prometheus-and-grafana-on-ubuntu/) para poder hacer esta parte.

**Prometheus** es un sistema de monitoreo de aplicaciones de codigo abierto que consigue metricas del servidor en intervalos regulares y puede monitorear su propio server como el de un cliente externo. Cada cliente debera correr su propia herramienta de recopilacion de metricas para poner sus estadisticas y tendra que ser de esta forma. Este usa el protocolo HTTP y para usarlo es recomendable su propia herramienta de exportador de nodos. Prometheus tambien recoge una gran cantidad de datos incluyendo CPU y usos de memoria.

**Grafana** es una aplicacion de visualizacion de codigo abierto y empresarial. En vez de colleccionar la informacion lo que hace es usar la informacion recopilada por Prometheus o otra fuente de datos en un formato mas intuitivo y visual presentado en un panel de informacion definido como plantilla. Este tiene diferentes plantillas y permite a los usuarios crear sus propias plantillas y correr sus propias consultas, tmabien puede conectarse con bases de datos SQL o NoSQL y tener aplicaciones para aplicar tiquet como Jira y GitLab.

La descarga de este servicio la realizaremos desde su pagina de [GitHub](https://github.com/prometheus/prometheus).

### Download and Install Prometheus.

1. Visitaremos la pagina web de [Prometheus](https://prometheus.io/download/) para averiguar cual es la version actual.
2. Descargaremos Prometheus usando wget y ls direccion de su github. ``wget [https://github.com/prometheus/prometheus/releases/download/v2.37.6/prometheus-2.37.6.linux-amd64.tar.gz](https://github.com/prometheus/prometheus/releases/download/v2.37.6/prometheus-2.37.6.linux-amd64.tar.gz)`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_12.55.10_PM.png)
    
     
    
3. Ahora extraeremos el archivo Prometheus con `tar xvfz prometheus-*.tar.gz` y despues de extraerlo podemos eliminar el archivo comprimido si lo deseamos con `rm`.
    
    ![Y despues podremos eliminar el archivo comprimido.](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_12.57.53_PM.png)
    
    Y despues podremos eliminar el archivo comprimido.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_1.00.34_PM.png)
    
     
    
4. Crearemos dos diferentes directorios con `sudo mkdir`, el primero sera `/etc/prometheus` el cual guardara los archivos de configuracion y `/var/lib/prometheus` que guardara los datos de la aplicacion.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-10_at_1.06.06_PM.png)
    
     
    
5. Ahora entraremos al directorio de prometheus que descomprimimos y seguido a eso moveremos los directorios `prometheus` y `promtool` al directorio `/usr/local/bin/` para hacer a prometheus accesible a todos los usuarios con `sudo mv prometheus promtool  /usr/local/bin/`
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_2.25.19_PM.png)
    
     
    
6. Ahora moveremos la configuracion YAML `prometheus.yml` al directorio `/etc/prometheus` con `sudo mv prometheus.yml /etc/prometheus`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_2.31.28_PM.png)
    
     
    
7. Moveremos los directorios `consoles` y `consoles_libraries` y lo moveremos al directorio `/etc/prometheus` con `sudo mv consoles consoles_libraries /etc/prometheus`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_2.36.17_PM.png)
    
     
    
8. Finalmente comprobaremo la version de prometheus con `prometheus —version`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_2.38.24_PM.png)
    
     
    

### Configurar Prometheus como servicio.

Prometheus puede ser empezado y parado desde la linea de comando pero es mas conveniente correr el servicio utilizando la utilidad de `systemctl`.

Para comenzar a usar ete servicio necesitaremos añadir una configuracion extra al archivo `prometheus.yml`.

1. Al estar usando el puerto 9090 deberemos activar en el ufw este dicho puerto con el comando `sudo ufw allow 9090` y comprobamos que se haya añadidio correctamente con `sudo ufw status`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_4.51.00_PM.png)
    
     
    
2. Al mismo timepo deberemos añadir el puerto 9090 en Configuracion de VirtualBox → Red → Avanzadas → Reenvio de Puertos.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_6.20.05_PM.png)
    
     
    
3. Crearemos un usuario de prometheus con `sudo useradd -rs /bin/false prometheus` y proseguiremos dandole la propiedad de los dos directorios que hemos creado con el comando `sudo chown -R prometheus: /etc/prometheus /var/lib/prometheus`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_2.47.04_PM.png)
    
     
    
4. Para permitir que Prometheus corra un servicio creamos el archivo `prometheus.service` en el directorio `/etc/systemd/system/` y le añadiremos el siguiente contenido con el comando `sudo vi /etc/systemd/system/prometheus.service`:
    
    ```c
    [Unit]
    Description=Prometheus
    Wants=network-online.target
    After=network-online.target
    
    [Service]
    User=prometheus
    Group=prometheus
    Type=simple
    Restart=on-failure
    RestartSec=5s
    ExecStart=/usr/local/bin/prometheus \
        --config.file /etc/prometheus/prometheus.yml \
        --storage.tsdb.path /var/lib/prometheus/ \
        --web.console.templates=/etc/prometheus/consoles \
        --web.console.libraries=/etc/prometheus/console_libraries \
        --web.listen-address=0.0.0.0:9090 \
        --web.enable-lifecycle \
        --log.level=info
    
    [Install]
    WantedBy=multi-user.target
    ```
    
    - The `Wants` and `After` options must be set to `network-online.target`.
    - The `User` and `Group` fields must both be set to `prometheus`.
    - The `ExecStart` parameter explains where to find the `prometheus` executable and defines the default options.
    - The `config.file` option defines the location of the Prometheus configuration file as `/etc/prometheus/prometheus.yml`.
    - `storage.tsdb.path` tells Prometheus to store application data in the `/var/lib/prometheus/` directory.
    - `web.listen-address` is set to `0.0.0.0:9090`, allowing Prometheus to listen for connections on all network interfaces.
    - The `web.enable-lifecycle` option allows users to reload the configuration file without restarting Pro
        
        ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_4.19.13_PM.png)
        
         
        
5. Ahora recargamos el `systemctl daemon` con `sudo systemctl daemon-reload`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_4.21.07_PM.png)
    
     
    
6. Podremos configurar prometheus para que se inicie el servicio automaticamente con el comando `sudo systemctl enable prometheus`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_4.23.04_PM.png)
    
     
    
7. A continuacion iniciaremos el servicio de prometheus con `sudo systemctl start prometheus` y revisaremos que este activo `sudo systemctl status prometheus`.
    
    Si al iniciar el servicio falla deberemos usar `journalctl -u prometheus -f —no-pager` y revisar la salida de errores.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_4.33.38_PM.png)
    
     
    
8. Para acceder al panel de control de Prometheus iremos a la direccion de `[localhost:9090](http://localhost:9090)`.
    
    ![ ](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_6.24.20_PM.png)
    
     
    
9. Para ver todos los objetivos que indica el Prometheus vamos a `Status` y vemos los `Targets`.
    
    ![Screen Shot 2023-10-11 at 6.27.32 PM.png](./7%20-%20Bonuses%20Prometheus%20%26%20Grafana/Screen_Shot_2023-10-11_at_6.27.32_PM.png)
    
10. En este punto ya estaria el proyecto terminado con todos los bonuses necesarios para la maxima puntuacion del proyecto, espero que les haya podidio ayudar en todo lo posible.