# 🔍 Monitor de Conectividad por Ping

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Estado](https://img.shields.io/badge/Estado-Finalizado-blue)
![Sistema](https://img.shields.io/badge/SO-Windows-lightgrey)

Este es un programa de escritorio en Python que permite monitorear el estado de conexión de múltiples dispositivos en red mediante ping. Fue diseñado con una interfaz gráfica Tkinter, pensado especialmente para entornos donde se requiere supervisar equipos de comunicación como routers, switches, estaciones de peaje o centros de monitoreo.

---

## 📚 Tabla de contenido

- [¿Qué hace el programa?](#qué-hace-el-programa)
- [Captura de pantalla](#captura-de-pantalla-simulada)
- [Estructura del archivo de entrada](#estructura-del-archivo-de-entrada)
- [¿Cómo se usa?](#cómo-se-usa)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Requisitos](#requisitos)
- [Archivos generados](#archivos-generados)
- [Configuraciones modificables](#configuraciones-modificables)
- [Autor](#autor)
- [Licencia](#licencia)

---

## ✅ ¿Qué hace el programa?

- ✅ Carga una lista de IPs y nombres desde un archivo de texto.
- ✅ Consulta continuamente (cada 2 minutos) el estado de cada dispositivo mediante ping (modificable).
- ✅ Muestra en rojo los dispositivos que no responden.
- ✅ Emite una alerta sonora y visual solo cuando la pérdida de comunicación se mantiene por más de 4 minutos (modificable).
- ✅ Evita emitir alertas en un horario restringido (entre las 00:05 y 01:30 AM) (modificable).
- ✅ Registra automáticamente las pérdidas en un archivo de texto y en un Excel.
- ✅ Mantiene un historial ordenado de caídas.
- ✅ Tiene indicadores visuales del estado del sistema (parpadeo verde/rojo).

---

## 🖼️ Captura de pantalla (simulada)

![Captura](https://imgur.com/a/PNgqXep)

---

## 🗂️ Estructura del archivo de entrada

El archivo que se carga debe ser un `.txt` con el siguiente formato:


192.168.1.1  R  Router_Principal

192.168.1.10 SW Switch_Central


## ¿Cómo se usa?

1. Abre el programa.
2. Haz clic en **"Cargar IPs"** y selecciona el archivo `.txt` con las IPs.
3. Presiona **"Iniciar Consulta"**.
4. El sistema comenzará a monitorear. Si alguna IP no responde por más de 4 minutos, se te notificará (a menos que esté en horario restringido).
5. Puedes **detener la consulta** en cualquier momento con el botón correspondiente.
6. Si ocurre una alerta, presiona **"Reconocer Alarmas"** para detener el sonido.

-------

## Tecnologías utilizadas

- Python 3.x
- Tkinter (interfaz gráfica)
- `subprocess` (para ejecutar ping)
- `openpyxl` (para generar registros en Excel)
- `winsound` (para reproducir alertas en Windows)
- `threading`, `datetime`, `platform`, `time`

-------

## Requisitos

- Windows (funcionalidad probada en Windows 10/11)
- Python instalado
- Librerías necesarias (instalables con pip):

```bash
pip install openpyxl


## Archivos generados
historial_perdidas.txt: Registro cronológico en texto plano de los eventos de pérdida de conexión.
historial_perdidas.xlsx: Archivo Excel con columnas de Fecha y Hora, IP, Nombre de host y Estado.


⚙️ Configuraciones modificables
Estas opciones se pueden ajustar desde el código fuente:

⏱️ Intervalo de consulta por ping: time.sleep(120) → 2 minutos

📉 Umbral de inactividad antes de alertar: 2 ciclos consecutivos (4 minutos)

⏰ Horario restringido para alertas: entre las 00:05 y 01:30 AM

🔊 Sonido de alerta: se puede cambiar desde el archivo Alarm06.wav (ubicado en C:\Windows\Media)


👨‍💻 Autor
Desarrollado por NicolasRv88
🔗 https://github.com/NicolasRv88
🔗 www.linkedin.com/in/nicolasreyesvl


## 🧾 Licencia

Este proyecto está licenciado bajo la **MIT License**. Puedes usarlo, modificarlo y distribuirlo libremente.