# ATTINY_85

### Nicolás Sánchez Vargas

¡Bienvenido a este repositorio! Aquí aprenderás, paso a paso, todo lo necesario para construir con tus propias manos una consola de bolsillo impulsada por un microcontrolador.

# Consola portátil

En este proyecto se explora el funcionamiento del microcontrolador ATTINY85. Podrás escoger uno de los juegos incluidos en este repositorio o, si lo prefieres, cargar cualquier otro juego compatible con 8 bits. Para comprender este proyecto, pondremos en práctica algunos conocimientos básicos de electrónica.

## Materiales
-------------

- Protoboard  
>[![protoboard.jpg](https://i.postimg.cc/BnbD4JMd/protoboard.jpg)](https://postimg.cc/w1K3kYKV)

- ATTINY85  
>[![ATTINY-85.webp](https://i.postimg.cc/MGyG842C/ATTINY-85.webp)](https://postimg.cc/zLGNCxf7)

- Jumpers  
>[![jumpers.jpg](https://i.postimg.cc/fWFQBK1m/jumpers.jpg)](https://postimg.cc/3Wgqwg8x)

- Arduino UNO  
>![arduino](https://user-images.githubusercontent.com/79547422/206583391-c520780f-7c52-415b-9109-3f37045955c3.JPG)

- Pantalla OLED LCD I2C  
>[![Pantalla-Oled-Lcd-I2c.jpg](https://i.postimg.cc/h4JTkDZ6/Pantalla-Oled-Lcd-I2c.jpg)](https://postimg.cc/Hjgr5gg9)

- Pila CR2032  
>[![pila-cr2032.jpg](https://i.postimg.cc/W3ccsb68/pila-cr2032.jpg)](https://postimg.cc/QBmybDzK)

- Portabatería para pila CR2032  
>[![portapila-pila-cr-2032.jpg](https://i.postimg.cc/Nfk64Nzj/portapila-pila-cr-2032.jpg)](https://postimg.cc/bsdSYRP7)

- Pulsadores  
>[![pulsadores.jpg](https://i.postimg.cc/NfrsvMXy/pulsadores.jpg)](https://postimg.cc/2VrR4C2m)

- Resistencias de 1K x3  
>[![resistencia-1k.jpg](https://i.postimg.cc/g2zGXK5h/resistencia-1k.jpg)](https://postimg.cc/svNkb53f)

- Resistencia de 6.8K  
>[![resistencia-6-8k.jpg](https://i.postimg.cc/hvBkFDRm/resistencia-6-8k.jpg)](https://postimg.cc/34tSmHRr)

- Interruptor  
>[![suiche.jpg](https://i.postimg.cc/3xcz8CHY/suiche.jpg)](https://postimg.cc/w1DwFNvG)

- Zumbador  
>[![sumbador.jpg](https://i.postimg.cc/YqmdNKcK/sumbador.jpg)](https://postimg.cc/TpfjGsYC)

## Procedimiento
-------------

# Nuestro primer paso es programar el ATTINY85

Vamos a nuestro IDE de Arduino. Lo primero que debemos hacer es instalar la tarjeta del ATtiny85 para poder subir el código a nuestro controlador. Para ello, debemos ir a **“Archivo” → “Preferencias”**.

[![preferencias-de-arduin0.png](https://i.postimg.cc/bJPZWLcV/preferencias-de-arduin0.png)](https://postimg.cc/nsdVQ4Lq)

Donde dice **“URLs adicionales del gestor de placas”**, entramos y pegamos el siguiente enlace:

`https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json`

[![URL.png](https://i.postimg.cc/fR4D8yhB/URL.png)](https://postimg.cc/zVksBJvg)

[![URL-2.png](https://i.postimg.cc/9fL3HFv3/URL-2.png)](https://postimg.cc/8FfXhDpw)

Después de este proceso, se debe dar clic en **Aceptar** en ambas ventanas emergentes.

Este archivo JSON permitirá que nuestro IDE identifique el microcontrolador. Luego, debes ir a **“Herramientas” → “Placa” → “Gestor de placas”** para buscar **ATtiny** e instalarlo.

[![placa.png](https://i.postimg.cc/FsvQSqbB/placa.png)](https://postimg.cc/0rV3RVBY)

[![busqueda.png](https://i.postimg.cc/RFtj6QWm/busqueda.png)](https://postimg.cc/Ppt60DbV)

Cuando termine la descarga, se mostrará esta ventana:

[![descarga-completada.png](https://i.postimg.cc/DwDjr4kw/descarga-completada.png)](https://postimg.cc/BjTBs6nr)

Ahora cambiaremos la placa por la que descargamos. Iremos a **“Herramientas”**, buscamos donde dice **“Placa: Arduino Uno”**, nos dirigimos a **“ATtiny”** y escogemos **“ATtiny25/45/85”**.

[![cambio-de-placa.png](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

Continuamos cambiando el **Clock**. Para esto, nos dirigimos a **“Herramientas” → “Clock”** y escogemos **“Internal 8MHz”**.

[![cambio-de-clock.png](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)

Esta parte puede ser un poco confusa, pero iremos paso a paso. Lo primero es abrir un sketch nuevo. Vamos a **“Archivo” → “Ejemplos”** y buscamos **“Arduino ISP”**, el numeral 11, y lo seleccionamos.

[![ISP.png](https://i.postimg.cc/nrN5H3KB/ISP.png)](https://postimg.cc/JHcKxc2z)

Va a aparecer un código de ejemplo. Lo siguiente es ir a **“Herramientas”** y, en la sección de **“Placa”**, escoger nuestro Arduino, ya sea un **Arduino UNO, MEGA o Nano**.

[![subido-ejemplo.png](https://i.postimg.cc/SsPqM77N/subido-ejemplo.png)](https://postimg.cc/XG9TM5zT)

Un error común es la incorrecta comunicación entre el puerto USB del computador y el Arduino.

[![Error-de-puerto.png](https://i.postimg.cc/SNNj8Dhk/Error-de-puerto.png)](https://postimg.cc/QVwXZgCy)

Para solucionar eso, se debe ir a **“Herramientas” → “Puerto”** y escoger el puerto recomendado. En mi caso es **COM3**, pero puede variar en cada computador.

Luego nos dirigimos a **“Programador”** y verificamos que esté en la opción **“AVRISP mkII”**. Conectamos nuestro Arduino y subimos el archivo. Esto lo hacemos para indicarle al Arduino que funcionará como programador, ya que los microcontroladores necesitan uno para grabar la información en su memoria.

Ahora vamos a conectar nuestro IDE con el microcontrolador. Para ello vamos a usar la comunicación **ISP**, la cual explicaremos más a fondo en un video más adelante, pero para este proyecto te recomendamos seguir esta imagen:

>[![coneccion-arduino-PSI-a-ATTINY-85.png](https://i.postimg.cc/BnKvW8v5/coneccion-arduino-PSI-a-ATTINY-85.png)](https://postimg.cc/Snm4CxCj)

Para continuar, lo primero es ir a **“Herramientas” → “Placa”** y seleccionar **“ATtiny25/45/85”**. Luego, en el mismo menú de **“Herramientas”**, en **“Procesador”**, seleccionamos **“ATtiny85”**, que es nuestra placa. Después, en **“Clock”**, seleccionamos **8MHz**, que es la frecuencia a la que se van a comunicar nuestras tarjetas.

Ahora vamos a **“Herramientas”** y, en **“Programador”**, tenemos que seleccionar **“Arduino as ISP”**. Por último, debemos verificar que nuestro Arduino esté conectado a los puertos ISP tanto de la placa como del controlador. Verificado esto, nos vamos a **“Herramientas” → “Grabar Bootloader”**. Los LEDs que indican la comunicación **Rx/Tx** deben parpadear después de que el proceso esté completo.

[![cambio-de-placa.png](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

[![procesador.png](https://i.postimg.cc/sfZqDR8h/procesador.png)](https://postimg.cc/K4xJJCmG)

[![cambio-de-clock.png](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)

[![programador-ISP.png](https://i.postimg.cc/8P7RV1n2/programador-ISP.png)](https://postimg.cc/JGWDNW8x)

[![quemar.png](https://i.postimg.cc/JnNL0D4G/quemar.png)](https://postimg.cc/gX25B0hW)

Por fin vamos a poder subir nuestros juegos. Ten en cuenta que el proceso que acabamos de hacer solo se realiza una vez por cada microcontrolador que quieras programar. Ahora vamos a descargar el archivo ZIP con varios juegos creados por la comunidad, lo descomprimimos y abrimos cualquier juego. En nuestro caso, vamos a usar **“Space Attack”**.

Lo abres en tu IDE y debes asegurarte de que la configuración quede como la hicimos previamente: el programador en **“Arduino as ISP”**, el procesador en **ATtiny85** y el **Clock a 8MHz**. Si ya lo verificaste, entonces, con nuestro Arduino conectado y los puertos de comunicación ISP de la placa y el microcontrolador correctamente conectados, compilamos y subimos el archivo.

¡Listo! Ya tenemos toda la programación completa.

## Realizamos conexiones

Ya con nuestro microcontrolador programado, solo nos hace falta seguir este esquemático:

>[![conecciones.png](https://i.postimg.cc/W1tSvXsQ/conecciones.png)](https://postimg.cc/w18D55yV)

Cuando hayas terminado y corroborado las conexiones, podrás encenderlo y jugar con tu nueva consola portátil que tú mismo has creado.

# ¡FELICIDADES, LO CONSEGUISTE!

## Últimas recomendaciones
-------------

Si tienes alguna pregunta o inquietud, te puedes comunicar con nosotros:

- [Instagram]([https://www.instagram.com/zicam_tecnologia/](https://www.instagram.com/atlion_robotics?igsh=MTBndm1idTkwd29oaw%3D%3D&utm_source=qr))


## Créditos

- Nicolás Sánchez Vargas
- Juan Silva Medina
