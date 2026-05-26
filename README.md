# README — Informe Final del Sistema

## 1. Propósito del repositorio

Este repositorio contiene la estructura base para construir el **informe final del sistema**.  
El informe consolida los aportes técnicos de diferentes autores sobre los módulos, decisiones, restricciones, pruebas, problemas encontrados, ajustes realizados y aprendizajes derivados del desarrollo del sistema.

El documento debe servir como una memoria técnica organizada, clara y útil para:

- Documentar el diseño general del sistema.
- Explicar las decisiones técnicas tomadas.
- Registrar problemas encontrados y ajustes realizados.
- Facilitar la transferencia de conocimiento.
- Permitir que otros comprendan, repliquen, mantengan o continúen el desarrollo.
- Consolidar el aprendizaje derivado de la práctica.

Este repositorio usa únicamente dos archivos base:

```text
README.md
main.tex
```

Cada autor debe revisar cuidadosamente este README antes de escribir su sección en `main.tex`.

---

## 2. Regla principal de escritura

Cada capítulo debe responder cinco preguntas:

1. ¿Qué función cumple este componente o tema dentro del sistema?
2. ¿Cómo fue diseñado, implementado o estructurado?
3. ¿Qué problemas se presentaron durante su desarrollo o integración?
4. ¿Cómo se decidió qué ajuste, cambio o solución aplicar?
5. ¿Qué aprendizaje técnico o práctico deja esta parte del sistema?

El informe no debe limitarse a describir resultados finales.  
También debe documentar el proceso de decisión, los problemas, los cambios realizados y las razones técnicas detrás de cada ajuste.

---

## 3. Estructura general del informe

La estructura base del informe final será:

```text
1. Introducción general
2. Análisis de requerimientos, restricciones y uso
3. Diseño general del sistema
4. Hardware
5. SDR: adquisición y preprocesamiento de señales de radio en borde
6. Plataforma web en la nube
7. Análisis espectral y localización en la nube
8. Protocolos de prueba en nube y borde
9. Integración general del sistema
10. Aprendizajes derivados de la práctica y transferencia de conocimiento
11. Conclusiones generales
12. Recomendaciones
13. Referencias

Anexos
A. Técnica de desarrollo en grupo usando agentes IA
B. Enlaces a repositorios de software
C. Evidencias de pruebas
D. Diagramas complementarios
E. Glosario técnico
```

---

## 4. Estructura obligatoria para cada capítulo técnico

Cada capítulo técnico debe seguir esta estructura interna:

```text
X.1 Propósito del capítulo
X.2 Contexto dentro del sistema general
X.3 Desarrollo técnico
X.4 Entradas, salidas e interfaces
X.5 Decisiones de diseño o implementación
X.6 Problemas presentados y ajustes realizados
X.7 Validación, pruebas o evidencias
X.8 Aprendizajes y transferencia de conocimiento
X.9 Limitaciones
X.10 Recomendaciones específicas
```

Esta estructura debe aplicarse especialmente a los capítulos:

- Análisis de requerimientos, restricciones y uso.
- Diseño general del sistema.
- Hardware.
- SDR: adquisición y preprocesamiento en borde.
- Plataforma web en la nube.
- Análisis espectral y localización en la nube.
- Protocolos de prueba en nube y borde.
- Integración general del sistema.

---

## 5. Apartado obligatorio: problemas presentados y ajustes realizados

Cada capítulo debe incluir un apartado titulado:

```text
Problemas presentados y ajustes realizados
```

Este apartado debe documentar:

- Problema identificado.
- Evidencia del problema.
- Causa probable.
- Alternativas consideradas.
- Criterio usado para tomar la decisión.
- Ajuste o cambio realizado.
- Resultado posterior al ajuste.
- Aprendizaje obtenido.

Formato sugerido:

| Problema | Evidencia | Causa probable | Alternativas consideradas | Decisión tomada | Justificación | Resultado |
|---|---|---|---|---|---|---|
| Describir problema | Log, prueba, captura, error | Explicación técnica | Opciones evaluadas | Cambio aplicado | Razón de la decisión | Estado final |

Ejemplo:

| Problema | Evidencia | Causa probable | Alternativas consideradas | Decisión tomada | Justificación | Resultado |
|---|---|---|---|---|---|---|
| Pérdida de muestras durante adquisición SDR | Logs de captura incompleta | Bloques de adquisición demasiado grandes | Reducir sample rate, reducir bloque, cambiar buffer | Reducir tamaño de bloque y ajustar buffer | Disminuye carga de memoria sin perder resolución suficiente | Captura estable |

---

## 6. Información que debe entregar cada autor

Cada autor debe completar su capítulo con información suficiente para que el informe pueda compilarse de forma completa y coherente.

Cada sección debe incluir, cuando aplique:

### 6.1 Texto técnico

- Descripción clara del tema.
- Relación con el sistema general.
- Decisiones tomadas.
- Restricciones identificadas.
- Problemas encontrados.
- Ajustes realizados.
- Resultados obtenidos.
- Limitaciones.
- Recomendaciones.

### 6.2 Tablas

Toda tabla debe tener:

- Número.
- Título.
- Descripción.
- Fuente.
- Unidades, si aplica.
- Variables claramente definidas.

Ejemplo:

```text
Tabla X. Parámetros de adquisición SDR.
Fuente: elaboración propia.
```

### 6.3 Figuras y diagramas

Toda figura debe tener:

- Número.
- Título.
- Descripción.
- Fuente.
- Explicación dentro del texto.

Ejemplo:

```text
Figura X. Arquitectura general del sistema.
Fuente: elaboración propia.
```

Las figuras no deben aparecer aisladas.  
Toda figura debe ser mencionada y explicada en el texto.

### 6.4 Gráficas

Toda gráfica debe indicar:

- Variable del eje X.
- Variable del eje Y.
- Unidades.
- Condiciones de la prueba.
- Fecha o contexto de adquisición, si aplica.
- Interpretación del resultado.

Ejemplo:

```text
La Figura X muestra la PSD estimada para una captura en la banda FM. Se observa una emisión dominante alrededor de ___ MHz, con un ancho de banda aproximado de ___ kHz.
```

### 6.5 Evidencias

Las evidencias pueden incluir:

- Capturas de pantalla.
- Logs.
- Resultados de pruebas.
- Tablas comparativas.
- Diagramas de flujo.
- Mediciones.
- Reportes generados por la plataforma.

Cada evidencia debe explicar:

- Qué muestra.
- Por qué es relevante.
- Qué conclusión permite obtener.

### 6.6 Referencias

Toda fuente externa debe estar referenciada.

Pueden citarse:

- Manuales técnicos.
- Datasheets.
- Documentación oficial.
- Artículos científicos.
- Libros.
- Repositorios.
- Normas.
- Documentación de librerías.
- Documentación de APIs.

Se recomienda usar estilo IEEE.

---

## 7. Formación o preparación mínima sugerida para los autores

Para que el informe quede completo y técnicamente coherente, cada autor debe revisar previamente los conceptos mínimos asociados a su capítulo.

### 7.1 Autor del capítulo de requerimientos, restricciones y uso

Debe conocer o revisar:

- Levantamiento de requerimientos.
- Requerimientos funcionales y no funcionales.
- Casos de uso.
- Restricciones técnicas, económicas y operativas.
- Criterios de aceptación.
- Matriz de trazabilidad.
- Riesgos del sistema.

Debe entregar:

- Tabla de requerimientos funcionales.
- Tabla de requerimientos no funcionales.
- Casos de uso principales.
- Restricciones del sistema.
- Supuestos.
- Criterios de aceptación.

### 7.2 Autor del capítulo de diseño general del sistema

Debe conocer o revisar:

- Arquitectura de sistemas.
- Diseño modular.
- Arquitecturas borde-nube.
- Flujo de datos.
- Interfaces entre módulos.
- Diagramas de bloques.
- Diagramas de despliegue.
- Escalabilidad.
- Seguridad básica.

Debe entregar:

- Diagrama general del sistema.
- Diagrama de flujo de datos.
- Descripción de módulos.
- Interfaces entre módulos.
- Justificación de la arquitectura.
- Problemas de integración previstos o encontrados.

### 7.3 Autor del capítulo de hardware

Debe conocer o revisar:

- Componentes RF básicos.
- Antenas.
- SDR.
- Computadores de borde.
- Alimentación eléctrica.
- Consumo de corriente.
- Conectividad.
- Limitaciones físicas del montaje.
- Ruido, saturación y rango dinámico.

Debe entregar:

- Tabla de componentes.
- Diagrama de conexión.
- Requisitos de alimentación.
- Restricciones del hardware.
- Limitaciones conocidas.
- Recomendaciones de operación.

### 7.4 Autor del capítulo SDR: adquisición y preprocesamiento en borde

Debe conocer o revisar:

- Señales IQ.
- Frecuencia central.
- Tasa de muestreo.
- Ganancia.
- FFT.
- PSD.
- Welch.
- Preprocesamiento de señales.
- Manejo de buffers.
- Formatos de datos.
- Envío de datos hacia la nube.
- Limitaciones del SDR usado.

Debe entregar:

- Flujo de adquisición.
- Parámetros de configuración.
- Formato de datos generado.
- Explicación del preprocesamiento.
- Evidencias de captura.
- Problemas encontrados.
- Ajustes aplicados.
- Enlace al repositorio real del software.

### 7.5 Autor del capítulo de plataforma web en la nube

Debe conocer o revisar:

- Arquitectura web.
- Frontend.
- Backend.
- APIs.
- Bases de datos.
- Usuarios y roles.
- Seguridad básica.
- Visualización de datos.
- Despliegue en cloud.
- Logs y monitoreo.

Debe entregar:

- Arquitectura de la plataforma.
- Descripción de funcionalidades.
- Modelo general de datos.
- Capturas de la plataforma.
- Flujo de usuario.
- Restricciones.
- Enlace al repositorio real del software.

### 7.6 Autor del capítulo de análisis espectral y localización en la nube

Debe conocer o revisar:

- Procesamiento digital de señales.
- Estimación espectral.
- PSD.
- Periodograma.
- Welch.
- Detección de emisiones.
- Umbrales.
- Estimación de frecuencia central.
- Estimación de ancho de banda.
- Geolocalización o localización, si aplica.
- Métricas de desempeño.
- Validación de resultados.

Debe entregar:

- Flujo de procesamiento.
- Métodos usados.
- Parámetros configurables.
- Resultados generados.
- Gráficas o tablas de validación.
- Problemas encontrados.
- Ajustes realizados.
- Enlace al repositorio real del software.

### 7.7 Autor del capítulo de protocolos de prueba en nube y borde

Debe conocer o revisar:

- Diseño de pruebas.
- Pruebas unitarias.
- Pruebas de integración.
- Pruebas extremo a extremo.
- Pruebas de hardware.
- Pruebas de conectividad.
- Métricas de validación.
- Criterios de aceptación.
- Registro de evidencias.

Debe entregar:

- Matriz de pruebas.
- Protocolos paso a paso.
- Criterios de aprobación.
- Evidencias.
- Resultados obtenidos.
- Problemas encontrados.
- Ajustes realizados.

### 7.8 Autor del anexo sobre desarrollo en grupo usando agentes IA

Debe conocer o revisar:

- Uso responsable de herramientas de IA.
- Ingeniería de prompts.
- Revisión humana de contenido.
- Control de calidad.
- Trazabilidad de decisiones.
- Riesgos de alucinación.
- Validación técnica de salidas generadas por IA.
- Buenas prácticas de documentación asistida por IA.

Debe entregar:

- Descripción del flujo de trabajo con IA.
- Roles asignados a los agentes.
- Ejemplos de uso.
- Beneficios.
- Riesgos.
- Mecanismos de validación humana.
- Buenas prácticas.

---

## 8. Regla sobre software y código

Si en el informe se menciona software, scripts, notebooks, aplicaciones, APIs, módulos, librerías propias o herramientas desarrolladas por el grupo, **no se debe incluir el código completo dentro del informe final**.

En su lugar, se debe:

1. Explicar qué hace el software.
2. Explicar sus entradas y salidas.
3. Explicar cómo se integra al sistema.
4. Mostrar diagramas, flujos o pseudocódigo conceptual si es necesario.
5. Incluir el enlace al repositorio real donde está alojado el código.
6. Indicar versión, rama, commit o release cuando sea posible.

Formato recomendado:

```text
Nombre del software:
Repositorio:
Rama o versión:
Responsable:
Función dentro del sistema:
Entradas:
Salidas:
Dependencias principales:
Estado actual:
```

Ejemplo:

```text
Nombre del software: Módulo de adquisición SDR en borde
Repositorio: https://github.com/organizacion/repositorio-sdr-borde
Rama o versión: main / v1.0
Responsable: Nombre del autor
Función dentro del sistema: adquisición IQ, preprocesamiento y envío de datos
Entradas: señal RF recibida por SDR, parámetros de adquisición
Salidas: archivos PSD, metadatos y paquetes enviados a la nube
Dependencias principales: Python, NumPy, SciPy, librería SDR correspondiente
Estado actual: funcional / en prueba / pendiente de integración
```

No incluir bloques largos de código en el informe.  
Solo se permiten fragmentos muy breves si son necesarios para explicar una configuración o un comando, pero el código fuente completo debe permanecer en el repositorio correspondiente.

---

## 9. Sugerencias para fortalecer la transferencia de conocimiento

Además de documentar el sistema, se recomienda que cada capítulo incluya elementos que ayuden a otros a aprender desde la experiencia práctica.

### 9.1 Lecciones aprendidas

Cada capítulo debe incluir una subsección de aprendizaje práctico.

Debe responder:

- ¿Qué se aprendió durante el desarrollo?
- ¿Qué error no era evidente al inicio?
- ¿Qué decisión fue clave?
- ¿Qué recomendación se daría a un nuevo integrante?
- ¿Qué conceptos técnicos se entendieron mejor a partir de la práctica?

### 9.2 Buenas prácticas

Cada autor debe documentar buenas prácticas relacionadas con su módulo.

Ejemplos:

- Buenas prácticas de adquisición SDR.
- Buenas prácticas de despliegue cloud.
- Buenas prácticas de diseño de pruebas.
- Buenas prácticas de documentación.
- Buenas prácticas de integración borde-nube.
- Buenas prácticas de uso de IA en desarrollo colaborativo.

### 9.3 Errores frecuentes

Cada capítulo debe indicar errores frecuentes o fallas comunes.

Ejemplos:

- SDR no reconocido por el sistema operativo.
- Saturación por exceso de ganancia.
- Pérdida de muestras por buffers insuficientes.
- Latencia elevada por envío excesivo de datos.
- Gráficas mal interpretadas por falta de unidades.
- Fallas de comunicación con la nube.
- Falta de sincronización entre módulos.

### 9.4 Guía de reproducción

Cuando aplique, cada capítulo debe explicar cómo reproducir una prueba o resultado.

Debe incluir:

- Condiciones iniciales.
- Parámetros usados.
- Datos requeridos.
- Pasos principales.
- Resultado esperado.
- Evidencia esperada.
- Repositorio asociado.

### 9.5 Glosario técnico

Se recomienda alimentar el glosario del informe con términos como:

- SDR.
- IQ.
- PSD.
- FFT.
- Welch.
- Frecuencia central.
- Sample rate.
- Ganancia.
- Borde.
- Cloud.
- API.
- Backend.
- Frontend.
- Localización.
- Latencia.
- Protocolo de prueba.
- Integración extremo a extremo.

### 9.6 Matriz de trazabilidad

Se recomienda relacionar:

```text
Requerimiento → Módulo → Implementación → Prueba → Evidencia
```

Ejemplo:

| Requerimiento | Módulo | Implementación | Prueba | Evidencia |
|---|---|---|---|---|
| Capturar señales RF | SDR borde | Módulo de adquisición | PR-001 | Log y PSD generada |
| Visualizar resultados | Plataforma web | Dashboard | PR-010 | Captura de pantalla |

---

## 10. Criterios mínimos de calidad

Antes de entregar una sección, cada autor debe verificar:

- La sección está conectada con el sistema general.
- Se explica claramente el propósito del módulo o tema.
- Se describen entradas y salidas.
- Se justifican las decisiones técnicas.
- Se documentan problemas y ajustes.
- Se incluyen evidencias o pruebas.
- Se mencionan limitaciones.
- Se registran aprendizajes prácticos.
- Las tablas tienen título y descripción.
- Las figuras tienen título, fuente y explicación.
- Las gráficas tienen ejes, unidades e interpretación.
- Las referencias están completas.
- Si se menciona software, se enlaza al repositorio real.
- No se incluye código fuente completo en el informe.

---

## 11. Convenciones de escritura

Usar redacción técnica clara.

Evitar:

- Texto genérico sin conexión con el sistema.
- Afirmaciones sin evidencia.
- Figuras sin explicación.
- Tablas sin unidades.
- Código largo dentro del informe.
- Referencias incompletas.
- Descripciones vagas como “se hicieron pruebas” sin indicar cuáles.

Preferir:

- “Se implementó...”
- “Se observó...”
- “El problema identificado fue...”
- “La decisión se tomó porque...”
- “La evidencia obtenida fue...”
- “El ajuste permitió...”
- “La principal limitación es...”
- “El aprendizaje derivado fue...”

---

## 12. Convenciones sobre repositorios de software

Cuando se mencione un componente de software, usar enlaces reales.

Formato recomendado en el texto:

```text
El módulo de adquisición SDR se encuentra disponible en el repositorio:
https://github.com/organizacion/nombre-repositorio

La versión documentada corresponde a la rama `main`, commit `________`.
```

Si todavía no existe un repositorio real, escribir:

```text
Repositorio pendiente de publicación.
```

No inventar enlaces.

---

## 13. Estado sugerido de cada sección

Cada capítulo puede tener uno de estos estados:

| Estado | Descripción |
|---|---|
| Pendiente | No se ha iniciado |
| En desarrollo | El autor está escribiendo |
| En revisión | Ya fue entregado para revisión |
| Requiere ajustes | Tiene observaciones pendientes |
| Aprobado | Está listo para integrarse |
| Integrado | Ya fue incluido en el informe final |

---

## 14. Recomendación final para los autores

Cada autor debe escribir pensando en una persona que no participó directamente en el desarrollo, pero que necesita entender:

- Qué se hizo.
- Por qué se hizo así.
- Qué problemas aparecieron.
- Cómo se corrigieron.
- Cómo se prueba.
- Qué aprendió el grupo.
- Dónde está el software real.
- Qué queda pendiente.

El informe final debe funcionar como documento técnico, memoria de decisiones y herramienta de transferencia de conocimiento.
