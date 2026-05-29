# Requerimientos finales del sistema ANE-HX

Proyecto para la Agencia Nacional del Espectro (ANE) de Colombia.

## 1. Arquitectura de la solución

### 1.1. Seguridad de la información
- Información en tránsito: usar SSL/TLS para toda la transferencia entre el sensor y la interfaz de monitoreo.

## 2. Funciones generales

### 2.1. Parametrización

**Adquisición:**
- Frecuencia central: ingreso manual desde 1 MHz hasta 6 GHz (o límite del hardware).
- Sample Rate: seleccionable, hasta 20 MS/s (mínimo 200 kS/s).
- Rango de frecuencias: frecuencia central + ancho de banda instantáneo (máx. 20 MHz, mín. 2 MHz).
- Redundancia GPS: parametrización manual adicional de ubicación geográfica, conservando la del GPS.

**Visualización:**
- RBW ajustable mediante selección de puntos FFT: RBW = Sample Rate / FFT Size.
- VBW: suavizado del espectro (bajo, medio, alto).
- Rechazo fuera de banda: filtros por software (pasabajo, pasabanda, pasaalto) con fc, BW y activación/desactivación.
- Pasos de cambio de resolución: pasos de 500 Hz, resolución hasta 10 Hz.
- Unidades de medida seleccionables: frecuencia (Hz, kHz, MHz, GHz), potencia (dBm —prioritario—, dBmV, dBuV, V, W), campo eléctrico (dBuV/m —prioritario—, dBmV/m, mV/m, W/m², dBW/m²/MHz).
- Umbrales de detección: definir umbral a partir de 3 dB, 5 dB u otro valor configurable por el usuario.

### 2.2. Medición, visualización y audio

- Indicadores espectrales: traza máxima, traza mínima, promedio, RMS, máximo, mínimo.
- Marcadores: al menos 4 marcadores individuales y tipo delta, con cálculo de delta de potencia y delta de frecuencia.
- Medición de ancho de banda: método -X dB (X seleccionable: 3, 10 o 26 dB) y OBW (99% de potencia).
- Potencia de canal: para emisiones de hasta 20 MHz.
- Radiodifusión sonora: demodular y escuchar FM y AM. Medir profundidad de modulación AM y excursión de frecuencia FM.

### 2.3. Cumplimiento normativo (detección de emisiones)

Usar bases de datos de operadores autorizados por banda para verificar:
1. Detección de frecuencias sin uso (ausencia de emisiones autorizadas).
2. Detección de emisiones no autorizadas (contra base de datos del MinTIC).
3. Incumplimiento de ancho de banda (señales fuera de límites autorizados).

**Servicios adicionales para radiodifusión sonora (88-108 MHz) y servicio móvil aeronáutico (108-137 MHz):**
- Recolección de datos para identificación de intermodulaciones desde 1 MHz.
- Detección de emisiones desviadas respecto a la frecuencia central autorizada.

### 2.4. Funciones avanzadas

- Recolección de datasets y entrenamiento para procesos de análisis posteriores.

### 2.5. Herramientas de gestión

- Monitoreo de sensores/estaciones remotas: alertas sobre violación de umbrales de variables (disco, RAM, etc.).
- Monitoreo de conectividad: calidad de conexión IP (RTT, estado alive/not alive).
- Agenda de programaciones: publicar agenda de escaneos, mantener sesiones privadas, permitir cancelar escaneos programados (rol supervisor).
- Generación automática de informes: al menos 1 reporte con variables definidas por la entidad, en CSV.

### 2.6. Análisis forense

- Referenciación de información: timestamp + geotags + identificador del sensor.
- Almacenamiento en sensores: archivos de muestreo (.cs8).
- Almacenamiento en servidores ANE (tierra): resultados de monitoreo programado en servidores institucionales.

### 2.7. Red

- WiFi: habilitar conexión.
- Ethernet: puerto de red cableado conservando características ambientales.
- Enrutamiento automático: seleccionar automáticamente el canal de comunicación disponible (Ethernet, WiFi u otro).

### 2.8. Soporte

- Acceso remoto a sensores vía IP para actualización de software y parches.

## 3. Hardware

### 3.1. GPS
- Conexión móvil mediante SIM card institucional para transmisión de datos.
- No dependencia de tecnologías propietarias.
- Precisión horizontal ≤ 10 m, vertical ≤ 15 m (estándar L1 GNSS civil EE. UU.).

### 3.2. Antenas
- Multiplexación de antenas: board que permita usar 4 antenas distintas en adquisición.
- Kit de 3 antenas por sensor:
  1. TDT
  2. Telefonía móvil (Down link, f > 2 GHz)
  3. VHF/UHF y frecuencias intermedias

### 3.3. EMC
- Optimizar susceptibilidad electromagnética para evitar interferencias que falseen mediciones (optimización SDR).

## 4. Exactitud y confiabilidad

### 4.1. Confiabilidad de medidas
- Sincronización NTP en cada sensor para etiquetado de muestreos.
- Procedimientos de calibración: frecuencia, ganancia de recepción, IQ balance y corrección de offset. Verificar con equipos certificados.

### 4.2. Caracterización del sistema
- DANL: determinar el nivel más bajo de señal detectable sin señal presente.
- Rango dinámico: diferencia entre señal máxima sin distorsión y mínima detectable sobre ruido (DANL).
- Exactitud de frecuencia: diferencia máxima aceptable entre frecuencia real y medida.
- Precisión de amplitud: margen de error en medición de potencia (dB).

## 5. Interoperabilidad

- Exportación de datos: escaneos descargables en formato CSV, JSON y XML para procesamiento offline.

---

## Entregables esperados

Con base en los requerimientos, el sistema ANE-HX debe entregar:

1. **Nodo de sensado en borde (hardware):** Raspberry Pi 5 + HackRF One + MonRaF2 (concentrador RF, LTE, GNSS, mux de antenas) + kit de antenas. Conectividad WiFi, Ethernet y celular con enrutamiento automático. GPS con precisión ≤ 10 m.

2. **Software del sensor (SDR):** adquisición IQ parametrizable, preprocesamiento (balance IQ, corrección DC, calibración), estimación de PSD, demodulación FM/AM, medición de ancho de banda (-X dB, OBW), potencia de canal, marcadores, umbrales de detección configurables.

3. **Plataforma web en la nube:** frontend SPA + backend de orquestación + base de datos TimescaleDB. Autenticación, monitoreo en tiempo real vía WebSocket, gestión de campañas, generación de reportes en CSV, agenda de programaciones, monitoreo de sensores y conectividad.

4. **Módulo de postprocesamiento espectral:** detección de emisiones, estimación de Fc, BW, potencia, MER/BER (TDT). Cumplimiento normativo contra bases de licencias del MinTIC con filtrado geográfico por código DANE/municipio. Exportación CSV, JSON, XML.

5. **Documentación técnica:** informe final (este repositorio) con memoria técnica, decisiones de diseño, problemas/ajustes, pruebas, aprendizajes y transferencia de conocimiento.

## Alcance actual vs. pendiente

Lo documentado en este informe cubre los capítulos 4 (HW), 5 (SDR), 6 (Plataforma cloud), 7 (Análisis espectral) y Anexo A (técnica de desarrollo con IA). Los capítulos 2, 3, 8, 9, 10, 11, 12 y anexos B, C, D permanecen como placeholders.
