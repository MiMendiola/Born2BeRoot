# 6 - Crontab

**Que es crontab?** Es un administrador de procesos en segundo plano. Los procesos indicados seran ejecutados en el momento que especifiques en el fichero crontab.

Para configurar este archivo deberemos usar `sudo crontab -u root -e`.

Y añadiremos `*/10 * * * * sh /ruta del script` para que se ejecute el script cada 10 min.

![ ](./6%20-%20Crontab/Screen_Shot_2023-10-10_at_8.13.21_PM.png)

Funcionamiento de cada parametro:

**m** → correcponde a los minutos. Comprendidos de 0 a 59.

**h** → corresponde a las horas comprendido entre 0 y 23 siendo 0 las 12 de la medianoche.

**dom** → es el dia del mes. Si pone 10, se ejecutara el dia 10 de ese mes.

**dow** → es el dia de la semana, corerspondido de 0(lunes) a 7(domingo) o las 3 primeras letras del dia en ingles: mon, tue, wed, thu, fri, sat, sun.

**user** → el usuario que va a ejecutar el comando.

**commando** → el script a ejecutar o su ruta.