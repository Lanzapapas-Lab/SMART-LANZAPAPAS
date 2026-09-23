# Lanzapapas

### IoT-based Experimental Telemetry and Control Platform

> **Status:** 🟡 Early development

Smart Cannon is an experimental engineering project focused on the instrumentation, telemetry, control and data analysis of a combustion-based launching platform.

The project combines concepts from **telecommunications engineering, embedded systems, Internet of Things (IoT), digital signal processing, sensor fusion, data analysis and experimental modelling**.

The objective is to progressively develop a complete measurement and telemetry platform capable of collecting, transmitting and analysing experimental data from the system.

---

## ⚠️ Safety

This repository is intended for **educational and experimental engineering purposes**.

The project involves a combustion-based experimental platform. Any physical experimentation must be carried out in a controlled environment using appropriate safety procedures, remotely operated systems where appropriate, and components rated for their intended operating conditions.

This repository focuses primarily on **instrumentation, sensing, telemetry, control, data acquisition and analysis**.

Detailed instructions for increasing projectile energy, range or destructive capability are intentionally outside the scope of this project.

---

# 1. Project Overview

The project is conceived as a modular experimental platform:

```text
                         ┌─────────────────────┐
                         │     DASHBOARD       │
                         │                     │
                         │ Telemetry           │
                         │ Experiments         │
                         │ Analysis            │
                         └──────────┬──────────┘
                                    │
                                  Wi-Fi
                                    │
                         ┌──────────▼──────────┐
                         │     IoT BACKEND     │
                         │                     │
                         │ MQTT                │
                         │ Database            │
                         │ API                 │
                         └──────────┬──────────┘
                                    │
                                  MQTT
                                    │
                    ┌───────────────▼───────────────┐
                    │             ESP32              │
                    │                               │
                    │      Experimental MCU         │
                    │                               │
                    │ ┌────────┐ ┌───────────────┐ │
                    │ │  IMU   │ │ Pressure      │ │
                    │ └────────┘ │ Temperature   │ │
                    │            │ Event sensors │ │
                    │            └───────────────┘ │
                    │                               │
                    │       Data Acquisition        │
                    │       Signal Processing       │
                    │       State Management        │
                    └───────────────────────────────┘
```

---

# 2. Main Objectives

The project will progressively address the following areas:

* Embedded systems
* Sensor integration
* Data acquisition
* Experimental telemetry
* IoT communications
* MQTT
* Digital signal processing
* Sensor fusion
* State estimation
* Computer vision
* Experimental modelling
* Statistical analysis
* Data visualisation
* PCB design

---

# 3. System Architecture

The system will be divided into several independent modules:

| Module              | Purpose                          | Status     |
| ------------------- | -------------------------------- | ---------- |
| ESP32               | Main embedded controller         | 🔴 Planned |
| IMU                 | Motion measurement               | 🔴 Planned |
| Pressure sensing    | Experimental pressure monitoring | 🔴 Planned |
| Temperature sensing | Thermal monitoring               | 🔴 Planned |
| Data logger         | Local experimental storage       | 🔴 Planned |
| Wi-Fi               | Wireless telemetry               | 🔴 Planned |
| MQTT                | IoT messaging                    | 🔴 Planned |
| Backend             | Data management                  | 🔴 Planned |
| Dashboard           | Monitoring and visualisation     | 🔴 Planned |
| Computer vision     | External motion measurement      | 🔴 Planned |
| Signal processing   | Filtering and estimation         | 🔴 Planned |
| PCB                 | Custom electronics               | 🔴 Planned |

Legend:

* 🟢 Completed
* 🟡 In progress
* 🔴 Planned
* ⚪ Not applicable

---

# 4. Repository Structure

```text
smart-cannon/
│
├── docs/              # Project documentation
├── firmware/          # ESP32 firmware
├── hardware/          # Electronics and PCB
├── software/          # Backend, analysis and dashboard
├── data/              # Experimental datasets
├── results/           # Figures and experimental results
│
├── README.md
├── LICENSE
└── .gitignore
```

More detailed documentation will be added progressively as each subsystem is developed.

---

# 5. Development Roadmap

### Phase 0 — Project definition

* [x] Define project concept
* [x] Define initial architecture
* [ ] Define system requirements
* [ ] Define measurement objectives

### Phase 1 — Embedded prototype

* [ ] ESP32 development environment
* [ ] IMU integration
* [ ] Basic sensor acquisition
* [ ] Local data logging
* [ ] Initial Python analysis

### Phase 2 — Instrumentation

* [ ] Pressure sensing
* [ ] Temperature sensing
* [ ] Event detection
* [ ] Sensor validation
* [ ] Measurement uncertainty

### Phase 3 — IoT

* [ ] Wi-Fi communication
* [ ] MQTT broker
* [ ] Telemetry protocol
* [ ] Backend
* [ ] Database

### Phase 4 — Signal Processing

* [ ] Filtering
* [ ] Sensor fusion
* [ ] Orientation estimation
* [ ] State estimation
* [ ] Experimental validation

### Phase 5 — Computer Vision

* [ ] Camera setup
* [ ] Object detection
* [ ] Motion tracking
* [ ] Trajectory reconstruction
* [ ] Comparison with sensor measurements

### Phase 6 — Hardware

* [ ] Electronics schematic
* [ ] PCB design
* [ ] Custom enclosure
* [ ] Hardware validation

### Phase 7 — Experimental Analysis

* [ ] Experimental protocol
* [ ] Dataset collection
* [ ] Statistical analysis
* [ ] Repeatability analysis
* [ ] Model validation

### Phase 8 — Final Documentation

* [ ] Technical report
* [ ] Final architecture
* [ ] Experimental results
* [ ] Conclusions
* [ ] Future work

---

# 6. Technology Stack

The technology stack is intentionally not fixed yet and will evolve during development.

### Embedded

* ESP32
* C/C++
* PlatformIO

### Communications

* Wi-Fi
* MQTT

### Backend

* Python
* FastAPI

### Data

* CSV
* JSON
* PostgreSQL / InfluxDB

### Analysis

* Python
* NumPy
* SciPy
* Pandas
* Matplotlib

### Computer Vision

* OpenCV

### Visualisation

* Grafana / custom dashboard

### Hardware

* KiCad

---

# 7. Experimental Data

Experimental data will be stored separately from source code.

```text
data/
├── raw/
├── processed/
└── metadata/
```

Each experiment should eventually have an associated identifier and metadata describing the experimental conditions and sensors used.

---

# 8. Documentation

Detailed documentation is located in [`docs/`](docs/).

The documentation will be developed alongside the project rather than written retrospectively.

---

# 9. Current Status

The project is currently in the **architecture and requirements definition stage**.

No final hardware configuration has been selected yet.

The next objective is to build the first minimal sensing prototype:

```text
ESP32
  │
  ▼
 IMU
  │
  ▼
Data acquisition
  │
  ▼
CSV
  │
  ▼
Python analysis
```

Once this subsystem is validated, additional sensors and communications will be progressively integrated.

---

# 10. Authors

**AlvGJ-UGR & Ch3sy**

Engineering students — Telecommunications Engineering

---

## License

This project is intended for educational and research purposes.
