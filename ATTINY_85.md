# 🕹️ ATtiny85 Pocket Console

<div align="center">

![ATtiny85](https://img.shields.io/badge/MCU-ATtiny85-orange?style=for-the-badge&logo=atmel&logoColor=white)
![Arduino IDE](https://img.shields.io/badge/Arduino_IDE-1.8%2B-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Language](https://img.shields.io/badge/Language-C%2FC%2B%2B-blue?style=for-the-badge&logo=cplusplus&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.0.0-blue?style=for-the-badge)

**Consola de videojuegos portátil construida desde cero con un microcontrolador ATtiny85, pantalla OLED y alimentada por una pila CR2032.**

[Juegos incluidos](#-juegos-incluidos) · [Hardware](#-hardware-requerido) · [Instalación](#-configuración-del-ide) · [Conexiones](#-diagrama-de-conexiones) · [Créditos](#-créditos)

</div>

---

## 📋 Tabla de Contenidos

- [¿Qué es este proyecto?](#-qué-es-este-proyecto)
- [Juegos incluidos](#-juegos-incluidos)
- [Hardware requerido](#-hardware-requerido)
- [Stack tecnológico](#-stack-tecnológico)
- [Configuración del IDE](#-configuración-del-ide)
- [Programar el ATtiny85](#-programar-el-attiny85)
- [Diagrama de conexiones](#-diagrama-de-conexiones)
- [Estructura del proyecto](#-estructura-del-proyecto)
- [Quick Start](#-quick-start)
- [Errores comunes](#-errores-comunes)
- [Roadmap](#-roadmap)
- [Contribuciones](#-contribuciones)
- [Créditos](#-créditos)
- [Licencia](#-licencia)

---

## 🎮 ¿Qué es este proyecto?

Una consola de bolsillo completamente funcional ensamblada sobre protoboard, programada con Arduino IDE y alimentada por el microcontrolador más pequeño de la familia AVR: el **ATtiny85**. Con tan solo 8 pines, 8KB de Flash y 512B de EEPROM, este proyecto demuestra cuánto se puede lograr con componentes mínimos.

Incluye **7 juegos retro** listos para cargar, una pantalla OLED I2C de 128×64 px, pulsadores de control, zumbador para audio y alimentación con pila de botón CR2032.

---

## 🕹️ Juegos Incluidos

| Archivo | Juego | Descripción |
|---|---|---|
| `SpaceAttackAttiny.ino` | 🚀 Space Attack | Shooter clásico de naves |
| `Tetris_Attiny_Arcade.ino` | 🟦 Tetris | El clásico de bloques |
| `Frogger_Attiny_Arcade.ino` | 🐸 Frogger | Cruza la calle sin morir |
| `BatBonanzaAttinyArcade.ino` | 🦇 Bat Bonanza | Esquiva obstáculos volando |
| `UFO_Stacker_Attiny.ino` | 🛸 UFO Stacker | Apila objetos con precisión |
| `MorseAttinyArcade.ino` | 📡 Morse | Juego de código Morse |
| `WrenRollercoasterAttinyArcade.ino` | 🎢 Wren Rollercoaster | Montaña rusa de alta velocidad |

> ⚙️ Cada juego es un sketch independiente — solo necesitas subir el que quieras jugar.

---

## 🔩 Hardware Requerido

| Componente | Cantidad | Descripción |
|---|---|---|
| ATtiny85 | 1 | Microcontrolador principal (DIP-8) |
| Arduino UNO | 1 | Usado como programador ISP (solo para grabar) |
| Pantalla OLED I2C 128×64 | 1 | Display SSD1306, protocolo I2C |
| Pulsadores | 3 | Controles del juego |
| Resistencias 1KΩ | 3 | Pull-down para los pulsadores |
| Resistencia 6.8KΩ | 1 | Divisor de voltaje / pull-up |
| Zumbador (buzzer) | 1 | Audio y efectos de sonido |
| Pila CR2032 | 1 | Alimentación portátil |
| Portabatería CR2032 | 1 | Soporte para la pila |
| Interruptor | 1 | Encendido / apagado |
| Protoboard | 1 | Ensamblado sin soldadura |
| Jumpers M-M | ~15 | Conexiones entre componentes |
| Capacitor 10µF | 1 | Evitar auto-reset del Arduino durante la carga |

---

## 🛠 Stack Tecnológico

| Capa | Tecnología | Versión |
|---|---|---|
| Microcontrolador | ATtiny85 (Atmel/Microchip) | — |
| IDE | Arduino IDE | `1.8+` |
| Board Package | damellis/attiny | `ide-1.6.x` |
| Lenguaje | C / C++ (Arduino) | — |
| Protocolo de programación | ISP (In-System Programming) | — |
| Comunicación display | I2C (TWI) | — |

---

## ⚙️ Configuración del IDE

### Paso 1 — Abrir preferencias

Abre Arduino IDE y ve a **Archivo → Preferencias**.

[![preferencias](https://i.postimg.cc/bJPZWLcV/preferencias-de-arduin0.png)](https://postimg.cc/nsdVQ4Lq)

### Paso 2 — Agregar la URL del board package

Donde dice **"URLs adicionales del gestor de placas"**, haz clic en el ícono de la derecha y pega el siguiente enlace:

```
https://raw.githubusercontent.com/damellis/attiny/ide-1.6.x-boards-manager/package_damellis_attiny_index.json
```

[![URL paso 1](https://i.postimg.cc/fR4D8yhB/URL.png)](https://postimg.cc/zVksBJvg)

[![URL paso 2](https://i.postimg.cc/9fL3HFv3/URL-2.png)](https://postimg.cc/8FfXhDpw)

Haz clic en **Aceptar** en ambas ventanas emergentes.

### Paso 3 — Instalar la placa ATtiny

Ve a **Herramientas → Placa → Gestor de placas**, busca `ATtiny` e instálalo.

[![gestor de placas](https://i.postimg.cc/FsvQSqbB/placa.png)](https://postimg.cc/0rV3RVBY)

[![búsqueda ATtiny](https://i.postimg.cc/RFtj6QWm/busqueda.png)](https://postimg.cc/Ppt60DbV)

Cuando termine la descarga verás esta confirmación:

[![descarga completada](https://i.postimg.cc/DwDjr4kw/descarga-completada.png)](https://postimg.cc/BjTBs6nr)

### Paso 4 — Configurar los parámetros de la placa

Ve a **Herramientas → Placa → ATtiny → ATtiny25/45/85**:

[![cambio de placa](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

Luego ve a **Herramientas → Clock** y selecciona **Internal 8MHz**:

[![cambio de clock](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)

---

## 🔌 Programar el ATtiny85

El ATtiny85 no tiene puerto USB propio, así que se programa usando un **Arduino UNO como ISP** (In-System Programmer). El proceso completo tiene tres fases y solo las dos primeras se hacen una sola vez.

---

### Fase 1 — Convertir el Arduino UNO en programador

**1.** Ve a **Archivo → Ejemplos → 11.ArduinoISP** y ábrelo:

[![ArduinoISP](https://i.postimg.cc/nrN5H3KB/ISP.png)](https://postimg.cc/JHcKxc2z)

**2.** Asegúrate de que la placa esté en **Arduino UNO** (o la que uses: MEGA, Nano):

[![placa Arduino UNO](https://i.postimg.cc/SsPqM77N/subido-ejemplo.png)](https://postimg.cc/XG9TM5zT)

**3.** Si aparece un error de puerto, ve a **Herramientas → Puerto** y selecciona el puerto correcto (en Windows suele ser `COM3`, pero puede variar):

[![error de puerto](https://i.postimg.cc/SNNj8Dhk/Error-de-puerto.png)](https://postimg.cc/QVwXZgCy)

**4.** Verifica que en **Herramientas → Programador** esté seleccionado **AVRISP mkII** y sube el sketch. Esto le indica al Arduino que funcionará como programador externo.

**5.** Añade un **capacitor de 10µF entre GND y RESET** del Arduino para evitar que se reinicie solo durante la carga.

---

### Fase 2 — Grabar el Bootloader al ATtiny85

Conecta el ATtiny85 al Arduino UNO siguiendo este diagrama:

[![conexión Arduino ISP a ATtiny85](https://i.postimg.cc/BnKvW8v5/coneccion-arduino-PSI-a-ATTINY-85.png)](https://postimg.cc/Snm4CxCj)

Luego configura el IDE así:

**Placa → ATtiny25/45/85:**

[![cambio de placa](https://i.postimg.cc/43fvqzC5/cambio-de-placa.png)](https://postimg.cc/v4K66xZg)

**Procesador → ATtiny85:**

[![procesador](https://i.postimg.cc/sfZqDR8h/procesador.png)](https://postimg.cc/K4xJJCmG)

**Clock → Internal 8MHz:**

[![clock 8MHz](https://i.postimg.cc/0yQ24QWS/cambio-de-clock.png)](https://postimg.cc/xcw2J0Sj)

**Programador → Arduino as ISP:**

[![programador ISP](https://i.postimg.cc/8P7RV1n2/programador-ISP.png)](https://postimg.cc/JGWDNW8x)

Por último, ve a **Herramientas → Grabar Bootloader**:

[![grabar bootloader](https://i.postimg.cc/JnNL0D4G/quemar.png)](https://postimg.cc/gX25B0hW)

Los LEDs Rx/Tx del Arduino parpadearán mientras se graba. Cuando terminen, ¡el ATtiny85 está listo!

> ✅ **Este proceso (Fases 1 y 2) solo se realiza una vez por cada microcontrolador.** A partir de aquí solo necesitas subir los sketches de los juegos.

---

### Fase 3 — Subir un juego

Con la misma configuración de la Fase 2 activa, abre cualquier `.ino` de este repositorio y haz clic en **Subir**. El sketch quedará grabado en el ATtiny85 y el juego iniciará automáticamente al encender la consola.

---

## 📐 Diagrama de Conexiones — Consola Final

Con el ATtiny85 ya programado, arma el circuito completo en la protoboard siguiendo este esquemático:

[![conexiones consola](https://i.postimg.cc/W1tSvXsQ/conecciones.png)](https://postimg.cc/w18D55yV)

> 📌 Cuando hayas terminado y verificado todas las conexiones, enciende el interruptor y podrás jugar con tu consola portátil.

---

## 📁 Estructura del Proyecto

```
ATTINY85/
│
├── SpaceAttackAttiny.ino               # 🚀 Space Attack
├── Tetris_Attiny_Arcade.ino            # 🟦 Tetris
├── Frogger_Attiny_Arcade.ino           # 🐸 Frogger
├── BatBonanzaAttinyArcade.ino          # 🦇 Bat Bonanza
├── UFO_Stacker_Attiny.ino              # 🛸 UFO Stacker
├── MorseAttinyArcade.ino               # 📡 Morse
├── WrenRollercoasterAttinyArcade.ino   # 🎢 Wren Rollercoaster
│
├── ATTINY_85.md                        # Guía de construcción detallada
├── games.md                            # Info adicional de juegos
└── README.md                           # Este archivo
```

---

## 🚀 Quick Start

```
1. Instala Arduino IDE 1.8+
2. Agrega el board package del ATtiny85 (ver sección de configuración)
3. Sube ArduinoISP a tu Arduino UNO
4. Conecta el ATtiny85 al Arduino según el diagrama ISP
5. Graba el Bootloader al ATtiny85
6. Abre cualquier .ino de este repo
7. Sube el sketch → ¡a jugar!
```

---

## ⚠️ Errores Comunes

| Error | Causa | Solución |
|---|---|---|
| `avrdude: stk500_recv()` | Puerto COM incorrecto | Ve a **Herramientas → Puerto** y selecciona el correcto |
| `programmer not responding` | Falta el capacitor 10µF | Añade el capacitor entre GND y RESET del Arduino |
| Pantalla en blanco | Dirección I2C incorrecta | Verifica si tu OLED usa `0x3C` o `0x3D` |
| El juego no inicia | Clock mal configurado | Confirma que el Clock esté en **Internal 8MHz** |
| Error de compilación | Placa incorrecta seleccionada | Verifica que la placa sea **ATtiny25/45/85** y procesador **ATtiny85** |

---

## 🗺 Roadmap

- [ ] PCB personalizado para la consola (reemplazar protoboard)
- [ ] Case / carcasa 3D imprimible
- [ ] Soporte para batería recargable (LiPo + TP4056)
- [ ] Agregar más juegos compatibles con 8KB de Flash
- [ ] Tutorial en video paso a paso en YouTube
- [ ] Versión con Digispark (ATtiny85 con USB integrado)

---

## 🤝 Contribuciones

¡Los PRs son bienvenidos! Si tienes un juego compatible o mejoras al hardware:

1. **Fork** este repositorio
2. Crea tu rama:
   ```bash
   git checkout -b feature/nuevo-juego
   ```
3. Commitea con mensajes descriptivos:
   ```bash
   git commit -m "feat: agregar juego Snake para ATtiny85"
   ```
4. Sube tu rama y abre un **Pull Request**

### Requisitos para agregar un juego nuevo

- Debe compilar para **ATtiny85 a 8MHz**
- No debe superar los **8KB de Flash**
- Debe funcionar con pantalla **SSD1306 I2C 128×64**
- Incluye una descripción breve del juego en el PR

---

## 👨‍💻 Créditos

**Nicolás Sánchez Vargas**
- GitHub: [@Nicolas211202](https://github.com/Nicolas211202)
- LinkedIn: [linkedin.com/in/nicolas-sanchez-56261522a](https://www.linkedin.com/in/nicolas-sanchez-56261522a/)

**Juan Silva Medina**

**Comunidad & Redes**
- Instagram: [@atlion_robotics](https://www.instagram.com/atlion_robotics?igsh=MTBndm1idTkwd29oaw%3D%3D&utm_source=qr)
- YouTube: [@zicamtech](https://www.youtube.com/@zicamtech)

> Los juegos incluidos fueron desarrollados originalmente por la comunidad de [electronoobs.com](https://electronoobs.com/eng_arduino_tut120_code1.php).

---

## 📄 Licencia

Distribuido bajo la licencia **MIT**. Consulta el archivo [`LICENSE`](./LICENSE) para más detalles.

```
MIT License — Copyright (c) 2025 Nicolás Sánchez Vargas
```

---

<div align="center">
  <sub>Hecho con ❤️, un microcontrolador de 8 pines y muchos jumpers · ¿Te gustó? Dale una ⭐ al repo</sub>
</div>
