# Smart Lanzapapas (Telemetría & IoT Spud Gun)

### High-Pressure Potato Cannon with ESP32 Telemetry and Control Platform

> **Status:** 🟡 Early development

Smart Cannon es un proyecto de ingeniería experimental enfocado en la instrumentación, control y análisis de datos del lanzamiento de un proyectil de patata. 

El objetivo principal es llevar al límite la potencia de un cañón de patatas ayudándonos de un **ESP32** para calcular el **porcentaje de gas óptimo**, monitorizar la **presión de la explosión** y enviar toda la telemetría vía **Wi-Fi**.

---

##  Safety Warning

Este repositorio tiene un propósito puramente **educativo y de ingeniería**. Trabajar con gases inflamables y presión conlleva riesgos. Toda experimentación debe realizarse en exteriores, con gafas de seguridad y mediante ignición remota.

---

##  Presupuesto y Materiales

El coste total de los materiales del cañón y el sistema de ignición es de **100 €**.

###  Hardware Base del Cañón y Combustión
* **Tubo PVC encolar ø125mm 16 atmósferas** - Cámara de combustión (20,76 €)
* **Tapón PVC ø125mm encolar PN16** - Cierre trasero (14,04 €)
* **Tubo PVC encolar ø63mm 16 atmósferas** - Cañón (3,90 €).
* **Reducción cónica PVC ø125-ø63mm PN16** - Unión de cámara y cañón (7,75 €).
* **ADHESIVO PVC-50 PRESIÓN** - Sellado de piezas (4,55 €).
* **Válvula agrícola - Tractor TR618A** - Entrada de gas/aire (2,09 €).
* **Urban Gas para Mecheros Rellenable (300ml)** - Combustible (5,99 €).

###  Sistema de Ignición de Alta Tensión
* **Bujía para motores de 4t Garland** - Generador de chispa (2,99 €)
* **Generador de Alto Voltaje** - Elevador de tensión para crear el arco (8,93 €)
* **Cable de Alto Voltaje** - Aislamiento de silicona para evitar fugas eléctricas (6,99 €)
* **Pipa de bujía y Abrazadera metálica** - Conexiones seguras a la bujía (11,99 €)
* **Pila 3,7 V** - Alimentación independiente para el generador de arco (5,30 €)

###  Electrónica y Control (Telecomunicaciones -*Análisis de Datos*)
* Microcontrolador ESP32 (Wi-Fi integrado)
* Sensor de Presión (para medir el pico de la explosión)
* Sensor de Temperatura
* Relé optoacoplado (para disparar el Generador de Alto Voltaje remotamente)
* IMU (para medir el retroceso del cañón)


##  Conceptos  de Teleco y Electrónica

Otro reto de este proyecto es la plataforma IoT montada sobre el cañón:

1. **Cálculo de Gas Óptimo:** Mediante sensores, el sistema calcula la mezcla estequiométrica perfecta midiendo la presión y temperatura antes de la ignición.
2. **Telemetría Wi-Fi (MQTT):** El ESP32 envía los datos de cada disparo en tiempo real a un Dashboard para su análisis.
3. **Control de Ignición:** Disparo remoto y seguro controlado desde un servidor web o app móvil activando el relé del Generador de Alto Voltaje.
4. **Análisis de la Explosión:** Adquisición de datos a alta frecuencia (DSP) del pico de presión en la cámara en el milisegundo de la deflagración.

---

##  Arquitectura del Sistema

```text
                         ┌─────────────────────┐
                         │     DASHBOARD       │
                         │ (Grafana / Web UI)  │
                         └──────────┬──────────┘
                                    │ Wi-Fi
                         ┌──────────▼──────────┐
                         │     IoT BACKEND     │
                         │    (MQTT Broker)    │
                         └──────────┬──────────┘
                                    │ MQTT
                    ┌───────────────▼───────────────┐
                    │             ESP32             │
                    │      (Control & Telemetry)    │
                    │                               │
                    │  [Pressure]  [Temperature]    │
                    │  [Ignition Relay]  [IMU]      │
                    └───────────────────────────────┘
```
## Tecnología

*  ESP32, python, PlatformIO
* **Comunicaciones:** Wi-Fi
* **Backend y Datos:** -----
* **Análisis y CV:** -----
* **Hardware:** -------

---

## Roadmap de Desarrollo

### Fase 0: Cálculos y selección materiales
* [ ] Selección de materiales óptimos.
* [ ] Simulaciones y cálculos termodinámicos.


### Fase 1: Prototipo Físico y Hardware
* [ ] Construcción del cañón.
* [ ] Implementación del sistema de ignición.

### Fase 2: Implementación de sensores
* [ ] Programación del ESP32.
* [ ] Integración de los sensores de forma segura.
* [ ] Calibración del sensor de presión y relé de disparo.
* [ ] Adquisición local de datos en tarjeta SD.

### Fase 3: IoT y Dashboard
* [ ] Integración de MQTT y Wi-Fi.
* [ ] Despliegue del Backend y Dashboard para disparo remoto.

### Fase 4: Análisis y Optimización Avanzado
* [ ] Cálculo dinámico del volumen de gas óptimo.
* [ ] Fusión de sensores (IMU + Presión) y análisis de trayectoria con cámaras.

---

## 📂 Estructura del Repositorio

Los datos experimentales de cada disparo (presión, retroceso, gas usado) se guardarán en `data/` separados del código fuente.

```text
smart-cannon/
├── docs/              # Documentación y esquemas eléctricos
├── firmware/          # Código C/C++ del ESP32
├── software/          # Servidor Python, MQTT y Dashboard
├── hardware/          # Materiales y componentes necesarios
├── results/           # Conclusiones de las versiones
├── data/              # Datasets de los disparos experimentales
├── README.md
└── LICENSE
