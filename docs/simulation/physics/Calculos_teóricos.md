# Estudio Termodinámico, Químico y Balístico de un Lanzador de Gas (Combustión de Butano)

> **Resumen Ejecutivo:** Este documento presenta el análisis técnico riguroso de un sistema de proyección por combustión atmosférica de butano ($C_4H_{10}$). Se evalúan la geometría óptima de los volúmenes, la estequiometría de la reacción, la dinámica de gases adiabática y la eficiencia balística interior.

| 

| **Parámetro Clave** | **Valor Teórico / Nominal** | **Unidad SI** | 
| **Relación de Volúmenes (**$C:B$**)** | $1.5 : 1.0$ | Admensional | 
| **Combustible** | n-Butano ($C_4H_{10}$) | \- | 
| **Presión Pico Téorica (**$P_1$**)** | $8.5 \text{ atm} \quad (861,262 \text{ Pa})$ | $\text{Pa}$ | 
| **Trabajo Teórico Expandido (**$W_{ideal}$**)** | $2,461$ | $\text{J}$ | 
| **Energía Cinética Efectiva (**$E_k$**)** | $369$ | $\text{J}$ | 
| **Velocidad de Salida (**$v$**)** | $121.5$ | $\text{m/s}$ | 

## 1. Diseño Geométrico Optimizado (Relación de Volúmenes $C:B$)

Para maximizar la transferencia de energía sin desperdiciar presión por una cámara sobredimensionada ni frenar el proyectil por vacío/succión en el cañón, se aplica la relación empírica óptima para cañones de gas atmosféricos:

$$
\text{Relación } C:B = \frac{V_c}{V_b} = 1.5
$$

Donde $V_c$ es el volumen de la cámara de combustión y $V_b$ es el volumen útil del cañón.

### 1.1. Volumen de la Cámara de Combustión ($V_c$)

Dada una cámara de PVC con diámetro interior $D_c = 113 \text{ mm} = 0.113 \text{ m}$ ($r_c = 0.0565 \text{ m}$) y longitud $L_c = 60 \text{ cm} = 0.60 \text{ m}$:

$$
V_c = \pi \cdot r_c^2 \cdot L_c = \pi \cdot (0.0565 \text{ m})^2 \cdot 0.60 \text{ m} \approx 0.00602 \text{ m}^3 = 6.02 \text{ L}
$$

### 1.2. Volumen del Cañón ($V_b$)

Aplicando la relación $C:B = 1.5$:

$$
V_b = \frac{V_c}{1.5} = \frac{6.02 \text{ L}}{1.5} = 4.01 \text{ L} = 0.00401 \text{ m}^3
$$

### 1.3. Longitud Óptima del Cañón ($L_b$)

Para un tubo de cañón con diámetro interior $D_b = 57 \text{ mm} = 0.057 \text{ m}$ ($r_b = 0.0285 \text{ m}$):

$$
A_b = \pi \cdot r_b^2 = \pi \cdot (0.0285 \text{ m})^2 \approx 0.0025518 \text{ m}^2
$$

$$
L_b = \frac{V_b}{A_b} = \frac{0.00401 \text{ m}^3}{0.0025518 \text{ m}^2} \approx 1.57 \text{ m}
$$

## 2. Termoquímica y Mezcla Estequiométrica

### 2.1. Reacción Balanceada de Combustión

La combustión completa del n-butano con oxígeno molecular ($O_2$) se expresa como:

$$
\text{C}_4\text{H}_{10} + 6.5\,\text{O}_2 \longrightarrow 4\,\text{CO}_2 + 5\,\text{H}_2\text{O}
$$

Dado que el aire atmosférico contiene aproximadamente un $20.95\%$ de $O_2$ por volumen ($\approx 1 \text{ mol de } O_2 \text{ por cada } 4.77 \text{ moles de aire}$):

$$
\text{Moles de aire requeridos por mol de } C_4H_{10} = \frac{6.5}{0.2095} \approx 31.03 \text{ moles}
$$

La fracción volumétrica ideal ($\chi_{gas}$) de butano en la mezcla aire-combustible es:

$$
\chi_{gas} = \frac{1 \text{ mol de } C_4H_{10}}{1 + 31.03 \text{ moles de mezcla}} \approx 0.03122 \quad \implies \quad 3.13\% \text{ en volumen}
$$

### 2.2. Cálculo del Volumen y Masa de Butano

El volumen de butano en estado gaseoso necesario para llenar la cámara de $6.02 \text{ L}$ es:

$$
V_{gas} = V_c \times \chi_{gas} = 6.02 \text{ L} \times 0.0313 = 0.188 \text{ L}
$$

Utilizando la ley de los gases ideales ($P V = n R T$) a $P = 1 \text{ atm}$ y $T = 20^\circ\text{C} = 293.15 \text{ K}$:

$$
n = \frac{P \cdot V_{gas}}{R \cdot T} = \frac{1 \text{ atm} \cdot 0.188 \text{ L}}{0.08206 \frac{\text{L}\cdot\text{atm}}{\text{K}\cdot\text{mol}} \cdot 293.15 \text{ K}} = 0.0078 \text{ moles}
$$

Con una masa molar del butano $M = 58.12 \text{ g/mol}$:

$$
m_{gas} = n \cdot M = 0.0078 \text{ moles} \times 58.12 \text{ g/mol} = 0.45 \text{ gramos}
$$

### 2.3. Dinámica de Inyección

Para una válvula de inyección comercial con un caudal promedio $\dot{m} = 1.5 \text{ g/s}$:

$$
t_{\text{inyección}} = \frac{m_{gas}}{\dot{m}} = \frac{0.45 \text{ g}}{1.5 \text{ g/s}} = 0.30 \text{ segundos}
$$

> \[!CAUTION\] **Riesgo de Ineficiencia:** Abrir la válvula durante períodos superiores (e.g., $2.0 \text{ s}$) inyectaría $\approx 3.0 \text{ g}$ de gas, creando una mezcla sobre-enriquecida fuera de los límites de inflamabilidad, impidiendo la detonación por falta de oxígeno.

## 3. Dinámica de Gases y Trabajo de Expansión Adiabática

Tras la ignición, la reacción química confinada genera un pico de presión teórica $P_1 = 8.5 \text{ atm} = 861,262 \text{ Pa}$.

El gas expande su volumen desde la cámara inicial ($V_1 = V_c = 0.00602 \text{ m}^3$) hasta el volumen total ($V_2 = V_c + V_b = 0.01003 \text{ m}^3$). Dado que la aceleración del proyectil ocurre en pocos milisegundos, la transferencia de calor hacia las paredes es insignificante ($Q \approx 0$), modelando el proceso como una **expansión adiabática reversible**:

$$
P(V) \cdot V^\gamma = \text{constante} = P_1 V_1^\gamma
$$

donde $\gamma \approx 1.3$ representa el coeficiente adiabático medio de los gases de combustión calientes ($\text{CO}_2, \text{H}_2\text{O}, \text{N}_2$).

### 3.1. Deducción Matemática del Trabajo ($W_{ideal}$)

El trabajo ejercido por el fluido sobre el proyectil se obtiene mediante la integral definida del producto presión-volumen:

$$
W_{ideal} = \int_{V_1}^{V_2} P(V) \, dV = \int_{V_1}^{V_2} (P_1 V_1^\gamma) V^{-\gamma} \, dV
$$

$$
W_{ideal} = P_1 V_1^\gamma \left[ \frac{V^{1-\gamma}}{1-\gamma} \right]_{V_1}^{V_2} = \frac{P_1 V_1^\gamma}{\gamma - 1} \left[ V_1^{1-\gamma} - V_2^{1-\gamma} \right]
$$

$$
W_{ideal} = \frac{P_1 V_1}{\gamma - 1} \left[ 1 - \left(\frac{V_1}{V_2}\right)^{\gamma-1} \right]
$$

### 3.2. Evaluación Numérica

1. **Término energético inicial:** 

   $$
   \frac{P_1 V_1}{\gamma - 1} = \frac{861,262 \text{ Pa} \times 0.00602 \text{ m}^3}{1.3 - 1} = \frac{5,184.8 \text{ J}}{0.3} = 17,282.6 \text{ J}
   $$

2. **Relación de expansión:** 

   $$
   1 - \left(\frac{V_1}{V_2}\right)^{\gamma-1} = 1 - \left(\frac{6.02 \text{ L}}{10.03 \text{ L}}\right)^{0.3} = 1 - (0.6002)^{0.3} = 1 - 0.8576 = 0.1424
   $$

3. **Trabajo Total Teórico:** 

   $$
   W_{ideal} = 17,282.6 \text{ J} \times 0.1424 = 2,461 \text{ Joules}
   $$

## 4. Eficiencia Balística y Velocidad del Proyectil

En un sistema real no idealizado, la conversión de trabajo termodinámico en energía cinética se ve reducida por una eficiencia mecánica ($\eta \approx 15\%$ o $0.15$).

```
Energía Química Disponible (2461 J)
 ├── Pérdidas por combustión no instantánea (~40%)
 ├── Fricción mecánica de extrusión (~25%)
 ├── Escapes de gas y sellado imperfecto ("Blow-by") (~20%)
 └── Energía Cinética Efectiva (15% -> 369 J)

```

### 4.1. Energía Cinética Efectiva ($E_k$)

$$
E_k = W_{ideal} \times \eta = 2,461 \text{ J} \times 0.15 = 369.15 \text{ Joules}
$$

### 4.2. Velocidad de Salida ($v$)

Para un proyectil cilíndrico estándar con masa $m = 50 \text{ g} = 0.050 \text{ kg}$:

$$
E_k = \frac{1}{2} m v^2 \implies v = \sqrt{\frac{2 E_k}{m}}
$$

$$
v = \sqrt{\frac{2 \times 369.15 \text{ J}}{0.050 \text{ kg}}} = \sqrt{14,766} \approx 121.5 \text{ m/s} \quad (\approx 437.4 \text{ km/h})
$$

## 5. Resumen de Magnitudes

| **Etapa** | **Ecuación Principal** | **Variable Resultado** | **Valor** | 
| **Geometría** | $L_b = \frac{V_c / 1.5}{\pi r_b^2}$ | Longitud Cañón ($L_b$) | $1.57 \text{ m}$ | 
| **Estequiometría** | $m = \frac{P V \chi M}{R T}$ | Masa Butano ($m$) | $0.45 \text{ g}$ | 
| **Termodinámica** | $W = \frac{P_1 V_1}{\gamma-1} \left[1-(\frac{V_1}{V_2})^{\gamma-1}\right]$ | Trabajo Teórico ($W_{ideal}$) | $2,461 \text{ J}$ | 
| **Balística Interior** | $v = \sqrt{\frac{2 W \eta}{m}}$ | Velocidad Salida ($v$) | $121.5 \text{ m/s}$ | 
