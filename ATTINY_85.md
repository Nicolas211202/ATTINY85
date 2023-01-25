# ATTINY_85

### Nicolas Sanchez Vargas 
¡Bienvenido a este repositorio! Aquí aprenderás paso a paso todo lo necesario para realizar con tus propias manos una consola de bolsillo inpulsado por un micro controlador.


# Consola portatil

En este proyecto se indaga en el funcionamiento del micro controlador ATTINY_85 para el cual podras escojer uno de los juegos que te dejo en este repositorio, en caso que ninguno sea de tu agrado puedes subir a el microcontrolador cualquier otro mientras que sea de 8 Bits, para poder comprender todo este proyecto pondremos en práctica algunos conosimientos basicos de la electronica.

## Materiales
-------------
- Protoboard
>[![protoboard.jpg](https://i.postimg.cc/BnbD4JMd/protoboard.jpg)](https://postimg.cc/w1K3kYKV)

- ATTINY_ 85
>[![ATTINY-85.webp](https://i.postimg.cc/MGyG842C/ATTINY-85.webp)](https://postimg.cc/zLGNCxf7)

- Jumpers
>[![jumpers.jpg](https://i.postimg.cc/fWFQBK1m/jumpers.jpg)](https://postimg.cc/3Wgqwg8x)

- Arduino UNO 
>![arduino](https://user-images.githubusercontent.com/79547422/206583391-c520780f-7c52-415b-9109-3f37045955c3.JPG)

Pantalla oled LCD I2C
>[![Pantalla-Oled-Lcd-I2c.jpg](https://i.postimg.cc/h4JTkDZ6/Pantalla-Oled-Lcd-I2c.jpg)](https://postimg.cc/Hjgr5gg9)

Pila cr2032
>[![pila-cr2032.jpg](https://i.postimg.cc/W3ccsb68/pila-cr2032.jpg)](https://postimg.cc/QBmybDzK)

Porta bataria para pila cr2032
>[![portapila-pila-cr-2032.jpg](https://i.postimg.cc/Nfk64Nzj/portapila-pila-cr-2032.jpg)](https://postimg.cc/bsdSYRP7)

Pulsadores
>[![pulsadores.jpg](https://i.postimg.cc/NfrsvMXy/pulsadores.jpg)](https://postimg.cc/2VrR4C2m)

REsistencia 1K x3
>[![resistencia-1k.jpg](https://i.postimg.cc/g2zGXK5h/resistencia-1k.jpg)](https://postimg.cc/svNkb53f)

REsistencia 6.8K
>[![resistencia-6-8k.jpg](https://i.postimg.cc/hvBkFDRm/resistencia-6-8k.jpg)](https://postimg.cc/34tSmHRr)

Interruptor
>[![suiche.jpg](https://i.postimg.cc/3xcz8CHY/suiche.jpg)](https://postimg.cc/w1DwFNvG)

zumbador
>[![sumbador.jpg](https://i.postimg.cc/YqmdNKcK/sumbador.jpg)](https://postimg.cc/TpfjGsYC)

Procedimiento
-------------

 # Nuestro primer paso es programar el ATTINY

Vamos a nuestro IDE de Arduino, lo primero que debemos hacer es instalar la tarjeta del ATtiny85 para que podamos subir el código en nuestro controlador, para eso debemos irnos a “archivo”, “preferencias” 

[![preferencias-de-arduin0.png](https://i.postimg.cc/bJPZWLcV/preferencias-de-arduin0.png)](https://postimg.cc/nsdVQ4Lq)

Donde dice “URLd adicionales de gestor de placas” entramos y pegamos el siguiente link " https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json " 

[![URL.png](https://i.postimg.cc/fR4D8yhB/URL.png)](https://postimg.cc/zVksBJvg)

[![URL-2.png](https://i.postimg.cc/9fL3HFv3/URL-2.png)](https://postimg.cc/8FfXhDpw)

Despues de estre poseso se deve darle aceptar en ambas ventanas emerjertes

, este es un archivo JSON que le permitirá a nuestro IDE identificar nuestro microcontrolador, luego debes irte a esta sección de “herramientas”, “placa” y “gestor de placas” para así buscar ATtiny e instalarlo,

[![placa.png](https://i.postimg.cc/FsvQSqbB/placa.png)](https://postimg.cc/0rV3RVBY)

[![busqueda.png](https://i.postimg.cc/RFtj6QWm/busqueda.png)](https://postimg.cc/Ppt60DbV)

Cuando termine la descarga se mostrara esta ventana 

[![descarga-completada.png](https://i.postimg.cc/DwDjr4kw/descarga-completada.png)](https://postimg.cc/BjTBs6nr)


 Ahora cambiaremos la placa por la que descargamos iremos a  "Heramientas" buscamos donde dice "Placa: "Arduino Uno" " nos dirigimos a "attiny" y escojemos " ATiny25/45/85"

 [![cambio-de-placa.png](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

Continuamos cambiendo el Clock para esto nos dirijimos a "Herramientas" vamos a " Clock " y escojemos " Internal 8MHz" 

[![cambio-de-clock.png](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)



Esta parte puede ser un poco confusa pero iremos paso a paso, lo primero es abrir un sketch nuevo, vamos a “archivo”, “ejemplos” y buscamos “Arduino ISP” el numeral 11, y lo seleccionamos,

[![ISP.png](https://i.postimg.cc/nrN5H3KB/ISP.png)](https://postimg.cc/JHcKxc2z)

 va a aparecer un código de ejemplo, lo siguiente es irnos a “herramientas” y en la sección de “placa” vamos a escoger nuestro Arduino, ya sea un Arduino UNO, MEGA o nano,
 
 [![subido-ejemplo.png](https://i.postimg.cc/SsPqM77N/subido-ejemplo.png)](https://postimg.cc/XG9TM5zT)

 Un error comun es la incorecta comunicacion enrte el puerto USB del computador y el arduino

 [![Error-de-puerto.png](https://i.postimg.cc/SNNj8Dhk/Error-de-puerto.png)](https://postimg.cc/QVwXZgCy)

 Para solocionar eso se debe ir a "Herramientas" , " Puerto " y escojemos el puerto que recomienda en mi caso es COM3 pero es todos es diferente 

  luego nos dirigimos a “programador” y verificamos que este en la opción "AVRISP mkII",
  
  
   conectamos nuestro Arduino, subimos nuestro archivo al Arduino, esto lo hicimos para decirle a nuestro Arduino que va a funcionar como un programador, ya que los microcontroladores necesitan de uno para grabar la información dentro de ellos.

Ahora vamos a conectar nuestro IDE con el microcontrolador, para ello vamos a usar la comunicación ISP la cual te explicaremos más a fondo un video más adelante, pero para este proyecto te recomendamos seguir esta imagen:

>[![coneccion-arduino-PSI-a-ATTINY-85.png](https://i.postimg.cc/BnKvW8v5/coneccion-arduino-PSI-a-ATTINY-85.png)](https://postimg.cc/Snm4CxCj)

Para continuar lo primero es ir a “herramientas”, “placa” y seleccionamos “ATtiny25/45/85”, luego en el mismo menú de “herramientas” en el “procesador” seleccionamos “ATtiny85” que es nuestra placa, y en el mismo menú en “Clock” seleccionamos la frecuencia del mismo que en nuestro caso es de 8MHz, que es a la frecuencia que se va a comunicar nuestras tarjetas, ahora vamos a “herramientas” y en “programador” tenemos que seleccionar "Arduino as ISP", y por ultimo debemos verificar que nuestro Arduino este conectado a nuestros puertos ISP  de la placa como del controlador, verificado esto nos vamos a “herramientas” y luego a “Grabar Bootloader” los leds que indican la comunicación Rx/Tx deben parpadear después de que el proceso este completo.

 [![cambio-de-placa.png](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

[![procesador.png](https://i.postimg.cc/sfZqDR8h/procesador.png)](https://postimg.cc/K4xJJCmG)

[![cambio-de-clock.png](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)

[![programador-ISP.png](https://i.postimg.cc/8P7RV1n2/programador-ISP.png)](https://postimg.cc/JGWDNW8x)

[![quemar.png](https://i.postimg.cc/JnNL0D4G/quemar.png)](https://postimg.cc/gX25B0hW)

Por fin vamos a poder subir nuestros juegos, ten en cuenta que el proceso que acabamos de hacer lo tienes que hacer solo una vez por cada microcontrolador que quieras programar, pero bueno, vamos a descargar este archivo ZIP con varios juegos creados por la comunidad, descomprimimos y abrimos un juego cualquiera, para nuestro caso vamos a usar “Space Attact” lo abres en tu IDE, debes asegurarte que la configuración quedo como lo hicimos previamente, y que el programador este en "Arduino as ISP", con el procesador ATtiny85, y el Clock a 8MHz, si ya lo verificaste entonces, con nuestro Arduino conectado y los puertos de comunicación ISP de la placa y el microcontrolador conectados compilamos y subimos nuestro archivo, y ¡LISTO ya tenemos toda la programación completa!

## Realizamos conexiones

Ya con muestro microcontrolador programado solo nos hace falta seguir este esquematico:

>[![conecciones.png](https://i.postimg.cc/W1tSvXsQ/conecciones.png)](https://postimg.cc/w18D55yV)

Ya cuendo allas logrado terminar y coroborar las conecciones podemos encenderlo y jugar con nuestra nueva consola portartil que tu mismo as creado !FELICIDADES LO CONSEGUISTE!


Ultimas recomendaciones 
-------------
Si tienes alguna pregunta o inquietud te puedes comunicar con nosotros.
-[instagram](https://www.instagram.com/zicam_tecnologia/)
-[youtube](https://www.youtube.com/@zicamtech)



## Creditos
- Nicolas Sanchez
- Juan Silva
