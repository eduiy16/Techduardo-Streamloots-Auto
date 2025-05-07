# Changelog

Todos los cambios importantes de este proyecto serán documentados en este archivo.

El formato está basado en [Keep a Changelog](https://keepachangelog.com/es/1.0.0/), y este proyecto sigue [Semantic Versioning](https://semver.org/lang/es/).

## [0.8.0] - 2025-05-06
### Añadido
- Se permite configurar la cantidad de cofres que se entregan según los meses de suscripción.
- Se puede definir cuántos cofres adicionales se asignan según el tipo de suscripción (Tier 1, Tier 2 o Tier 3).
- La configuración personalizada se guarda automáticamente y se aplica en cada ejecución del programa.
- Se reorganizó la interfaz del configurador para mantener claridad y orden con las nuevas opciones añadidas.

## [0.7.3] - 2025-04-14
### Added
- Se añadió soporte para incluir un icono personalizado en el archivo `.exe`.

## [0.7.2] - 2025-04-14
### Added
- Creado ejecutable `.exe` del programa usando PyInstaller para mayor comodidad del usuario.
- Incluido `Ejecutar_Cofres.py` dentro del `.exe` usando `--add-data`.
- `coordenadas.txt` y `CHANGELOG.md` se distribuyen junto al `.exe`, fuera del ejecutable.

## [0.7.1] - 2025-04-13
### Changed
- Implementadas rutas relativas seguras para asegurar que los archivos funcionen correctamente cuando se empaqueten como ejecutables (.exe) con PyInstaller.
- Añadida la función `ruta_local()` para calcular rutas internas de manera consistente.
- Modificados los accesos a `coordenadas.txt` para usar rutas relativas en ambos scripts.
- Actualizada la función `ejecutar_script()` para usar rutas relativas al ejecutar `Ejecutar_Cofres.py`.

## [0.7.0] - 2025-04-13
### Added
- Añadida la configuración de tecla de activación (por defecto F3) en la interfaz gráfica.
- Añadido un listener de teclas global que ejecuta automáticamente el script `Ejecutar_Cofres.py` al presionar la tecla configurada.
- La tecla de activación se almacena en el archivo de coordenadas como `TECLA_ACTIVACION`.
### Changed
- Actualizado el texto explicativo para incluir información sobre la tecla de activación.
- Reorganizada la interfaz para añadir el nuevo campo de configuración.

## [0.6.2] - 2025-04-13
### Changed
- Reordenados los campos en la interfaz gráfica de `guardar_coordenadas.py` para seguir el flujo lógico de la aplicación.
- Cambiada la etiqueta "Cerrar (X, Y):" a "Izq. Lupa (X, Y):".

## [0.6.1] - 2025-04-13
### Added
- Añadido el feedback del guardado.

## [0.6.0] - 2025-04-13
### Added
- Interfaz gráfica avanzada para la configuración de coordenadas en `guardar_coordenadas.py`.
  - Se permiten capturar coordenadas X e Y juntas al presionar F2 (en un único campo).
  - Se añadió un texto explicativo detallado (varias líneas) con instrucciones para configurar las coordenadas.
  - Las coordenadas se almacenan en un archivo JSON (`coordenadas.txt`) para su uso automático en el script principal.

## [0.5.0] - 2025-04-13
### Added
- División del proyecto en dos scripts independientes:
  - `guardar_coordenadas.py` para gestionar y guardar coordenadas.
  - `ejecutar_script.py` para ejecutar la automatización utilizando las coordenadas guardadas.
### Changed
- Adaptación del flujo principal para que lea las coordenadas desde el archivo JSON.

## [0.4.3] - 2025-04-13
### Changed
- Mejor ocultación de la consola: se modifica la minimización para ocultar la consola sin afectar la interfaz gráfica (usando `ShowWindow(..., 0)`).

## [0.4.2] - 2025-04-13
### Changed
- Interfaz gráfica mejorada para capturar coordenadas en un solo campo, permitiendo que X e Y se guarden juntos.

## [0.4.1] - 2025-04-13
### Added
- Evento global en la GUI para capturar la posición actual del mouse al presionar F2 y asignarla al campo activo.

## [0.4.0] - 2025-04-13
### Added
- Primera versión de la interfaz gráfica con Tkinter para configurar las coordenadas.
- Almacenamiento de coordenadas en JSON.
- Entradas para coordenadas individuales (X e Y separadas).

## [0.3.2] - 2025-04-13
### Changed
- Mejor manejo del portapapeles para separar la extracción del nick y el análisis completo del texto, evitando pérdida de información.

## [0.3.1] - 2025-04-13
### Changed
- Minimización automática de la ventana de consola usando `ctypes` (inicialmente se usó `ShowWindow(..., 6)`, luego se ajustó a ocultar la consola sin afectar la GUI).

## [0.3.0] - 2025-04-13
### Added
- Script unificado en Python que reemplaza el uso de Super Macro para la automatización completa.
- Automatización total del flujo: copiar texto, extraer el nick, pegar en Streamloots, reiniciar cofres y enviar.
- Uso de `pyautogui`, `pyperclip`, `time` y `ctypes` para controlar clicks, teclas y la interacción con la interfaz.

## [0.2.0] - 2025-04-13
### Added
- Separación del proceso de extracción del nick en un paso individual, manteniendo el texto completo en el portapapeles para análisis posterior.

## [0.1.0] - 2025-04-13
### Added
- Lógica avanzada para la entrega de cofres:
  - Detección de suscripciones "gifted" y "regalado".
  - Clasificación del número de meses de suscripción y asignación de cofres según rangos (1-5, 6-11, >12).
  - Adición de cofres adicionales basados en el tipo de suscripción (Prime, Tier 1, Tier 2, Tier 3).

## [0.0.0] - 2025-04-13
### Added
- Estructura base y automatización completa.
- Flujo inicial implementado para leer texto, detectar condiciones y enviar el resultado.
- Uso de `pyautogui`, `pyperclip`, `time` y `ctypes` en el script base.
