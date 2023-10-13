# 3 - Instalacion Debian

Antes de comenzar, agrandaremos la ventana para poder trabajar mejor. Deberemos darle al pc y pondremos el raton sobre `Virtual Screen 1` y la escalaremos a un 200%.

![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_6.58.35_PM.png)

 

## Comenzemos con la instalacion.

Para poder movernos por la instalacion usaremos las `Flechas` para movernos y el `Enter` para hacer algo que queramos confirmar.

1. Comenzaremos en movernos hasta `Instalar` y empezaremos con la instalacion pulsando `Enter`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.08.22_PM.png)
    
     
    
2. Usaremos el idioma predeterminado pero podras poder el idioma que desees, en nuestro caso usaremos ingles.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.11.49_PM.png)
    
     
    
3. Introducimos nuestro Pais o zona de residencia, en mi caso seleccionare `other`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.14.07_PM.png)
    
     
    
4. A continuacion seleccionamos nuestro continente, `Europe` en mi caso.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.14.32_PM.png)
    
     
    
5. Y por ultimo seleccionamos nuestro pais, `Spain` 🇪🇸.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.14.52_PM.png)
    
     
    
6. Ahora estableceremos nuestras configuraciones locales con `United States`. Esto tardara unos segundos en completarse.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.19.36_PM.png)
    
     
    
7. Seleccionaremos `American English` como configuracion de teclado para que no haya problemas en el futuro con las teclas.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.19.51_PM.png)
    
     
    
8. Aqui elegiremos el Host name de nuestra maquina. Tendra que ser tu `login + 42` al final.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.23.02_PM.png)
    
     
    
9. Saltaremos a la siguiente dejandolo vacio, ya que no mendinan nada de un Domain name.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.23.36_PM.png)
    
     
    
10. Añadiremos la constraseña para el administrador del sistema. Si quieres ver la contraseña solo tendras que `Tabular` hasta llegar a la opcion `Show Password in Clear` y pulsar `Espacio`. Tendremos que seguir estos pasaos para tener una constrseña valida:
    1. Debe tener al menos 10 caracteres.
    2. Debe contener al menos una letra mayúscula.
    3. Debe contener al menos una letra minúscula.
    4. Debe contener al menos un número.
    5. No debe contener más de 3 caracteres idénticos consecutivos.
    6. No debe incluir el nombre de usuario.
    7. Debe tener al menos 7 caracteres que no estuvieran en la contraseña anterior (esto no se aplica al root).
    
    Importante apuntar esta contraseña o hacerle una foto para no perderla. La contraseña mostrada es valida pero recomiendo usar otra nueva contraseña.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.32.40_PM.png)
    
     
    
11. Reescribimos la contraseña para confirmar que la escribimos bien.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.38.20_PM.png)
    
     
    
12. Tendremos que añadir un nuevo usuario a parte de el root del sistema, podreis llamarle como querais.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.44.42_PM.png)
    
     
    
13. Volveremos a escribir el nombre de usuario
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.44.59_PM.png)
    
     
    
14. Ahora haremos el mismo procedimiento para ponerle la contrasena a nuestro usuario.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.48.29_PM.png)
    
     
    
15. Y volveremos a confirmar la contraseña de nuestro usuario.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.49.02_PM.png)
    
     
    
16. Seleccionamos nuestra ubicacion. Y esperamos unos segundos.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.52.54_PM.png)
    
     
    
17. Si queremos seguir haciendo el proyecto sin hacer el bonus podeis ver como hacerlo en [*Sin Bonuses](https://github.com/gemartin99/Born2beroot-Tutorial#3--instalaci%C3%B3n-debian-).* En cambio si vamos ha hacerlo con bonuses deberemos seleccionar `Manual`. Con esto podremos editar las particiones de una vez.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-04_at_7.53.53_PM.png)
    
     
    
18. En este momento no tenemos ninguna particion hecha y para crearlas deberemos elegir el dispositivo en el cual queremos realizarlo. En nuestro caso escogeremos el único disponible.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_4.59.12_PM.png)
    
     
    
19. Este mensaje nos dice que si hay particiones realizadas en el dispositivo seran eliminadas y si estamos seguros de crear una nueva tabla de particiones vacia. `Aceptamos` el mensaje.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_4.59.36_PM.png)
    
     
    
20. Ahora seleccionaremos la nueva tabla de particiones que acabamos de realizar. 
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.04.51_PM.png)
    
     
    
21. Creamos una nueva particion
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.05.14_PM.png)
    
     
    
22. Como indica el pdf realizaremos la particion de `500m`
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.05.46_PM.png)
    
     
    
23. Como esta primera particion sera donde estara instalado el sistema operativo escogeremos la `Primaria`.
    
    Descripción breve de todos los tipos de [particiones](Tipos%20de%20Particiones.md).
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.07.53_PM.png)
    
     
    
24. Como queremos que se copie al principio seleccionaremos `Comienzo`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.09.08_PM.png)
    
     
    
25. Cambiaremos el punto del montaje de nuestra particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.12.50_PM.png)
    
     
    
26. Seleccionaremos boot como el punto de montaje de nuestra particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.15.40_PM.png)
    
     
    
27. Y terminamos de configurar la particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.15.50_PM.png)
    
     
    
28. Ya nos debe aparecer nuestra particion creada y a continuacion crearemos una particion logica.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.24.09_PM.png)
    
     
    
29. Creamos una nueva particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.24.38_PM.png)
    
     
    
30. Usamos el maximo del espacio disponible para esta particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.24.54_PM.png)
    
     
    
31. Ponemos que sea una particion `Logica`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.30.00_PM.png)
    
     
    
32. Modificamos el punto de montaje.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.33.06_PM.png)
    
     
    
33. Escogemos la opcion de no montarlo.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.33.51_PM.png)
    
     
    
34. Y terminamos de configurar esta particion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.34.03_PM.png)
    
     
    
35. Ahora comenzamos a configurar los `Volumenes Encriptados`, para encriptar nuestras particiones.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.35.11_PM.png)
    
     
    
36. Aceptamos el mensaje de confirmacion y esperamos unos segundos.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.35.18_PM.png)
    
     
    
37. Creamos los volumenes encriptados.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.36.47_PM.png)
    
     
    
38. Seleccionamos en que particion queremos la encriptacion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.37.20_PM.png)
    
     
    
39. Y terminamos la configuracion de la particion encriptada.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.38.23_PM.png)
    
     
    
40. Y con ese volumen encriptado terminamos dandole a `Terminar`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.39.10_PM.png)
    
     
    
41. Aceptamos el mensaje de cofirmacion donde nos dice que encriptara todo lo que hay en su interiory que no tardara mucho en terminar.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.40.33_PM.png)
    
     
    
42. Ya que la particion esta vacia no hay nada que encriptar asique le damos a `Cancelar`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.41.30_PM.png)
    
     
    
43. Ahora pondremos una contraseña que sera la frase de encriptacion.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.44.24_PM.png)
    
     
    
44. Repetimos la contraseña y esperamos unos segundos.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.44.54_PM.png)
    
     
    
45. Ahora seguiremos configurando el `Gestor de Volumenes Logicos`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.45.39_PM.png)
    
     
    
46. Aceptamos el mensaje de confirmacion ya que estamos de acuerdo que se cambien los cambios en el disco.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.47.47_PM.png)
    
     
    
47. Creamos un nuevo `grupo de volumen(agrupan particione)`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.50.00_PM.png)
    
     
    
48. Agregamos tal como nos indica el pdf el grupo con el nombre `LVMGroup`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.50.45_PM.png)
    
     
    
49. Y seleccionamos la particion donde crear el grupo.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.50.57_PM.png)
    
     
    
50. Ahora deberemos crear todas las particiones logicas necesarias. A continuacion podremos ver la secuencia de acciones que deberemos hacer y dejare la cantidad de gigas para cada particion.
    1. `root` - `10g`
    2. `swap` - `2.3g`
    3. `home` - `5g`
    4. `var` - `3g`
    5. `srv` - `3g`
    6. `tmp` - `3g`
    7. `var-log` - `4g`
    
    ![ Tienes que realizar estos pasos hasta haber completado todas las particiones.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.54.31_PM.png)
    
     Tienes que realizar estos pasos hasta haber completado todas las particiones.
    
    ![Seleccionamos el grupo donde lo crearemos, el unico disponible.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.57.56_PM.png)
    
    Seleccionamos el grupo donde lo crearemos, el unico disponible.
    
    ![Pondremos el nombre de la unidad logica. De root a var-log.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.58.07_PM.png)
    
    Pondremos el nombre de la unidad logica. De root a var-log.
    
    ![Lo siguiente sera el tamaño que usaremos para esa unidad.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_5.58.22_PM.png)
    
    Lo siguiente sera el tamaño que usaremos para esa unidad.
    
51. Una vez terminados todos, finalizaremos la configuracion del gestor de volumenes logicos.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.07.08_PM.png)
    
     
    
52. Ahora apareceran todas las particiones logicas que acabamos de crear. Deberemos configurarlas seleccionando el sistema de archivo que queremos y el punto de montaje respectivo para cada uno. Todos seran iguales menos `swap` y `var-log`
    
    ![Asi seran todas las particiones menos swap y var-log.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.15.05_PM.png)
    
    Asi seran todas las particiones menos swap y var-log.
    
    ![Debemos escoger un sistema de ficheros ya que no tiene en este momento](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.17.55_PM.png)
    
    Debemos escoger un sistema de ficheros ya que no tiene en este momento
    
    ![En todos los comunes seleccionaremos `Ext4 journaling file system` .](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.18.10_PM.png)
    
    En todos los comunes seleccionaremos `Ext4 journaling file system` .
    
    ![Ahora cambiaremos a su respectivo punto de montaje.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.18.19_PM.png)
    
    Ahora cambiaremos a su respectivo punto de montaje.
    
    ![En caso de home, seleccionaremos /home.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.18.25_PM.png)
    
    En caso de home, seleccionaremos /home.
    
    ![Y terminaremos con la configuracion.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.18.34_PM.png)
    
    Y terminaremos con la configuracion.
    
    ![Siendo swap seleccionaremos la swap area.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.22.05_PM.png)
    
    Siendo swap seleccionaremos la swap area.
    
    ![Y terminaremos con la configuracion de esta particion.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.23.02_PM.png)
    
    Y terminaremos con la configuracion de esta particion.
    
    ![Siendo var-log seguiremos los siguientes pasos.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.29.49_PM.png)
    
    Siendo var-log seguiremos los siguientes pasos.
    
    ![Debemos escoger un sistema de ficheros ya que no tiene en este momento](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.30.51_PM.png)
    
    Debemos escoger un sistema de ficheros ya que no tiene en este momento
    
    ![En todos los comunes seleccionaremos `Ext4 journaling file system` .](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.30.55_PM.png)
    
    En todos los comunes seleccionaremos `Ext4 journaling file system` .
    
    ![Ahora cambiaremos a su respectivo punto de montaje.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.31.03_PM.png)
    
    Ahora cambiaremos a su respectivo punto de montaje.
    
    ![Meteremos manualmente el punto de montaje.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.31.09_PM.png)
    
    Meteremos manualmente el punto de montaje.
    
    ![Metemos /var/log.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.31.32_PM.png)
    
    Metemos /var/log.
    
    ![Y terminamos con la ultima particion.](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.31.39_PM.png)
    
    Y terminamos con la ultima particion.
    
53. Terminados todos los pasos deberemos darla a finalizar el particionado y que se guarden todos los cambios.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.32.10_PM.png)
    
     
    
54. Ahora aceptaremos el mensaje y se guardaran los cambios realizados, aseguremonos que sean iguales a la captura. Este proceso tardara unos minutos.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.32.20_PM.png)
    
     
    
55. Seleccionamos la opcion `No` ya que no necesitamos paquetes adicionales.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.45.30_PM.png)
    
     
    
56. Escogemos nuestro pais.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.47.02_PM.png)
    
     
    
57. Escogeremos `deb.debian.org` que es donde tendremos una mejor conexion segun nuestra region.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.47.51_PM.png)
    
     
    
58. Le daremos a `Continue` y lo dejaremos vacio.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_6.49.09_PM.png)
    
     
    
59. Seleccionamos que `No` para que puedan ver las estadisticas.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_7.03.30_PM.png)
    
     
    
60. Quitaremos todas las opciones de software y le daremos a `Continue`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_7.03.59_PM.png)
    
     
    
61. Seleccionamos que `Si` para instalar `GRUB-PC` en el disco.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_7.04.56_PM.png)
    
     
    
62. Seleccionamos el dispositivo para arrancar nuestra instalacion `/dev/sda (ata_VBOX_HARDDISK)`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_7.05.03_PM.png)
    
     
    
63. Y finalmente le damos a `Continuar` para terminar nuestra instalacion de `Debian`.
    
    ![ ](./3%20-%20Instalacion%20Debian/Screen_Shot_2023-10-05_at_7.06.22_PM.png)
    
     
    
64. Y despues de esto, pasamos a configurar nuestra maquina virtual.