# 🕹️ ATtiny85 · Una consola en ocho pines

**Electrónica, programación y juegos retro en una consola de bolsillo.**

Proyecto de construcción de una microconsola basada en ATtiny85 y una pantalla OLED SSD1306. Este repositorio reúne una guía de montaje y siete sketches de la comunidad para explorar sistemas embebidos, entradas de usuario, gráficos y sonido con recursos limitados.

[Guía de construcción](ATTINY_85.md) · [Origen de los juegos](games.md) · [Perfil de Nicolás](https://github.com/Nicolas211202)

## Qué encontrarás

- Una guía ilustrada para preparar el entorno, programar el microcontrolador y montar la consola.
- Siete programas independientes en C/C++ para Arduino.
- Control de pantalla, pulsadores, sonido y, según el programa, almacenamiento en EEPROM y modos de reposo.

## Programas incluidos

| Programa | Archivo |
| :--- | :--- |
| Space Attack | [SpaceAttackAttiny.ino](SpaceAttackAttiny.ino) |
| Tetris | [Tetris_Attiny_Arcade.ino](Tetris_Attiny_Arcade.ino) |
| Frogger | [Frogger_Attiny_Arcade.ino](Frogger_Attiny_Arcade.ino) |
| Bat Bonanza | [BatBonanzaAttinyArcade.ino](BatBonanzaAttinyArcade.ino) |
| UFO Stacker | [UFO_Stacker_Attiny.ino](UFO_Stacker_Attiny.ino) |
| Decodificador Morse | [MorseAttinyArcade.ino](MorseAttinyArcade.ino) |
| Wren Rollercoaster | [WrenRollercoasterAttinyArcade.ino](WrenRollercoasterAttinyArcade.ino) |

Se carga **un programa a la vez**. El repositorio no incluye un menú que contenga los siete simultáneamente.

## Hardware

La guía de montaje utiliza un ATtiny85 DIP-8, una pantalla OLED SSD1306 de 128 × 64, pulsadores, zumbador, resistencias, alimentación con interruptor y un Arduino como programador ISP. Consulta los diagramas y la lista de componentes en [ATTINY_85.md](ATTINY_85.md).

Los sketches controlan la pantalla mediante PB4 para SCL y PB3 para SDA. Revisa las definiciones y los comentarios del programa elegido antes de cablear: algunos emplean una entrada adicional en RESET mediante un divisor resistivo.

## Antes de compilar

**Faltan tres archivos de fuentes gráficas en la versión actual del repositorio:**

| Cabecera | Programas que la necesitan |
| :--- | :--- |
| `font6x8AJ.h` | Space Attack, Bat Bonanza, UFO Stacker, Morse y Wren Rollercoaster |
| `font6x8AJ2.h` | Frogger |
| `font8x8AJ.h` | Tetris |

Estas cabeceras se incluyen con comillas en el código, pero no están versionadas aquí. Debes obtener la versión correspondiente del paquete original de cada programa y colocarla en la carpeta del sketch. El enlace de descarga de referencia se encuentra en [games.md](games.md). No se ha comprobado la disponibilidad actual de esos paquetes externos.

## Preparar y cargar un programa

1. Clona el repositorio:

   ```bash
   git clone https://github.com/Nicolas211202/ATTINY85.git
   cd ATTINY85
   ```

2. Elige un único `.ino` y cópialo a una carpeta con el mismo nombre sin extensión. Por ejemplo:

   ```text
   SpaceAttackAttiny/
   ├── SpaceAttackAttiny.ino
   └── font6x8AJ.h
   ```

   Mantener los siete `.ino` en la misma carpeta de sketch provoca que Arduino intente compilarlos juntos, con definiciones repetidas de `setup()`, `loop()` y otras funciones.

3. Instala en Arduino IDE un paquete de placas compatible con ATtiny85. La guía documenta el utilizado en el montaje original y la selección de reloj interno de 8 MHz.
4. Prepara el Arduino con el ejemplo **ArduinoISP** y realiza el cableado ISP siguiendo la guía.
5. Selecciona ATtiny85, el reloj apropiado y **Arduino as ISP**. La operación **Grabar bootloader** configura los fusibles del microcontrolador en este montaje; no añade un cargador USB.
6. Abre la carpeta del programa elegido, verifica la compilación y utiliza **Subir usando programador**.
7. Monta la consola siguiendo el esquema y comprueba sus controles.

## Estado del repositorio

La documentación y los sketches están disponibles para consulta. La compilación queda pendiente de recuperar las cabeceras faltantes; no se ha realizado una validación con hardware durante la preparación de este README.

La guía histórica contiene una declaración MIT y un enlace a `LICENSE`, pero ese archivo no está presente. Las condiciones de los programas originales deben revisarse por separado: varios encabezados indican uso no comercial con atribución. Este README no concede una licencia nueva sobre ese código.

## Créditos

La documentación de montaje acredita a **Nicolás Sánchez Vargas** y **Juan Silva Medina**.

Los encabezados de los sketches acreditan a **Andy Jackson**, al proyecto **AttinyArcade / webboggles**, a **Neven Boyanov / Tinusaur** por las rutinas de pantalla y a otros colaboradores por componentes concretos. Conserva los avisos y las atribuciones de cada archivo. [games.md](games.md) documenta Electronoobs como fuente de descarga utilizada.

## Próximas mejoras

- Recuperar las cabeceras gráficas respetando sus condiciones de distribución.
- Organizar cada programa en su propia carpeta de sketch.
- Verificar compilación y funcionamiento de cada programa en la consola.
- Añadir fotografías del montaje y una demostración de los controles.
