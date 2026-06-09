# README — Documento Pedagógico ANE

## 1. Propósito del repositorio

Este repositorio contiene el **informe final del sistema** del proyecto ANE. El documento integra los capítulos de hardware, software SDR, plataforma cloud y análisis espectral desarrollados durante el proyecto.

El informe final funciona como:

- Memoria técnica del sistema.
- Documento de integración de módulos.
- Registro de decisiones de diseño.
- Registro de problemas, ajustes y aprendizajes.
- Instrumento de transferencia de conocimiento.

La estructura del informe es modular:

```text
main.tex                 Archivo maestro. Solo editar para añadir/quitar capítulos.
README.md                Guía de estructura y procedimiento.
AGENTS.md                Instrucciones para agentes de IA que trabajen en el repo.
section/                 Un archivo .tex por capítulo.
section/img/             Imágenes por carpeta: cap04_hw/, cap05_sdr/, etc.
```

---

```markdown
## 3. Capítulos y anexos

La estructura actual del documento se organiza en capítulos principales y anexos. Cada archivo `.tex` se encuentra dentro de la carpeta `section/` y es incluido desde `main.tex` mediante el comando `\inputchapter{...}`.

| Archivo | Contenido | Estado actual |
|---|---|---|
| `section/1_introduction.tex` | Introducción general del informe | Incluido / escrito |
| `section/2_requirements-restrictions.tex` | Requerimientos, restricciones y alcance del sistema | Incluido / escrito |
| `section/3_general_design_system.tex` | Diseño general del sistema | Incluido / escrito |
| `section/4_HW.tex` | Hardware del nodo de sensado | Incluido / escrito |
| `section/5_SDR-acquisition.tex` | Software del sensor y adquisición SDR | Incluido / escrito |
| `section/6_Platform_cloud.tex` | Plataforma web en la nube | Incluido / escrito |
| `section/7_Spectral-localization_cloud.tex` | Análisis espectral y localización | Incluido / escrito |
| `section/8_Test_protocols_edge-cloud.tex` | Protocolos de prueba edge-cloud | Incluido / escrito |
| `section/9_System_integration.tex` | Integración general del sistema | Incluido / escrito |
| `section/10_General_conclusions.tex` | Conclusiones generales | Incluido / escrito |
| `section/11_Recommendations.tex` | Recomendaciones | Incluido / escrito |
| `section/12_References.tex` | Referencias | Incluido / escrito |
| `section/A_IA-collaboration-technique.tex` | Técnica de desarrollo con agentes de IA | Incluido / escrito |
| `section/B_Additional_diagrams.tex` | Diagramas adicionales | Incluido / parcial |
| `section/C_Manuals_guides.tex` | Manuales, guías y documentos de apoyo externos | Incluido / escrito |
| `section/D_Test_results.tex` | Resultados de pruebas | Incluido / por completar o validar |

### Observaciones sobre los anexos

Los anexos complementan el informe principal y deben mantenerse alineados con el contenido técnico de los capítulos:

- `A_IA-collaboration-technique.tex`: documenta la técnica de apoyo con agentes de IA utilizada durante el desarrollo documental.
- `B_Additional_diagrams.tex`: consolida diagramas adicionales que apoyan la comprensión del sistema.
- `C_Manuals_guides.tex`: referencia manuales, guías, videos, informes y documentos externos disponibles en Google Drive.
- `D_Test_results.tex`: debe consolidar resultados, evidencias y salidas de pruebas realizadas sobre el sistema.

### Documentación externa asociada

El anexo `section/C_Manuals_guides.tex` referencia la carpeta externa de documentación:

[Documentación ANE — Google Drive](https://drive.google.com/drive/folders/1Ne_Gym73XcDlqQFBKUjwLtbypIQ1od_t?usp=drive_link)

Los archivos de esta carpeta son documentos externos de consulta y no deben tratarse como archivos editables dentro del repositorio LaTeX. Entre los documentos disponibles se encuentran:

| Archivo externo | Tipo | Uso dentro del informe |
|---|---|---|
| `acceptance_test 1.0.pdf` | PDF | Pruebas de aceptación y criterios de validación |
| `Antena TDT ensamble.mp4` | Video | Apoyo al ensamble de antena TDT |
| `Antena VHF_UHF ensamble.mp4` | Video | Apoyo al ensamble de antena VHF/UHF |
| `Informe Técnico_ Análisis De Antenas.docx` | Documento Word | Soporte técnico para análisis de antenas |
| `Manual_del_Usuario.pdf` | PDF | Guía de operación para usuario final |
| `Anexo.pdf` | PDF | Material complementario |
| `Manual_del_administrador_de_la_plataforma.pdf` | PDF | Administración de la plataforma |
| `Documentación__soporte_del_sistema_de_monitoreo_multiproposito.pdf` | PDF | Soporte general del sistema de monitoreo |
| `manual_de_instalacion.pdf` | PDF | Instalación y despliegue |
| `informe_IQ_Balance.pdf` | PDF | Balance I/Q y soporte técnico SDR |
```

## 4. Cómo compilar

**Compilación automática (CI).** En cada push a `main`, el workflow
`.github/workflows/build-pdf.yml` compila `main.tex` con XeLaTeX. El PDF
resultante (`main.pdf`) queda disponible como artefacto del workflow
(descargable desde la pestaña Actions del repositorio).

**Compilación manual.**

Cada archivo de capítulo debe iniciar con `\chapter{...}` y debe contener, como mínimo, las siguientes secciones:

```latex
\chapter{Título del capítulo}

\section{Propósito del capítulo}
\section{Contexto dentro del sistema general}
\section{Desarrollo técnico}
\section{Entradas, salidas e interfaces}
\section{Decisiones de diseño o implementación}
\section{Problemas presentados y ajustes realizados}
\section{Validación, pruebas o evidencias}
\section{Aprendizajes y transferencia de conocimiento}
\section{Limitaciones}
\section{Recomendaciones específicas}
```

Los capítulos transversales como introducción, conclusiones, recomendaciones y referencias pueden tener una estructura diferente.

---

## 6. Figuras

Las figuras se guardan en `section/img/capXX_nombre/` y se insertan con:

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.85\textwidth]{section/img/cap04_hw/rpi5.png}
    \caption{Descripción. Fuente: elaboración propia.}
    \label{fig:rpi5}
\end{figure}
```

Toda figura debe tener `\caption`, `\label`, fuente y ser referenciada en el texto con `\ref{...}`.

---

## 7. Tablas

Usar `booktabs` + `tabularx`. No insertar tablas como imágenes.

```latex
\begin{table}[H]
\centering
\caption{Parámetros de adquisición SDR.}
\label{tab:params}
\begin{tabularx}{\textwidth}{@{}l X X@{}}
\toprule
Parámetro & Valor & Justificación \\
\midrule
Frecuencia central & 98 MHz & Banda de prueba. \\
Sample rate & 2.4 MS/s & Compatible con receptor. \\
Ganancia & 29.7 dB & Balance sensibilidad/saturación. \\
\bottomrule
\end{tabularx}
\end{table}
```

---

## 8. Software y repositorios

No se incluye código fuente completo en el informe. Usar el comando `\softwareRepo` o una tabla de repositorio con: nombre, URL, rama/versión, responsable, función, entradas, salidas y estado. Si el repositorio no existe: _"Repositorio pendiente de publicación"_. No inventar enlaces.

---

## 9. Referencias

Se consolidan en `section/12_References.tex`. Se recomienda estilo IEEE. Pueden citarse: manuales técnicos, datasheets, documentación oficial, libros, artículos, normas, repositorios.

---

```markdown
## 10. Criterio de calidad

Un capítulo se considera listo cuando una persona externa al desarrollo puede leerlo y entender:

- Qué componente, proceso o subsistema se documenta.
- Cómo se conecta con el sistema ANE-HX.
- Qué entradas, salidas e interfaces utiliza.
- Qué decisiones técnicas se tomaron.
- Qué problemas aparecieron durante el desarrollo o integración.
- Qué ajustes se aplicaron.
- Qué evidencias, pruebas, figuras o tablas respaldan el resultado.
- Qué limitaciones permanecen.
- Qué recomendaciones quedan para mantenimiento, mejora o continuidad.

Para los anexos, el criterio de calidad es que sirvan como soporte claro del informe principal. En particular, el anexo de manuales y documentos de apoyo debe permitir ubicar fácilmente los documentos externos, indicar su propósito y aclarar que son archivos de consulta no editables dentro del repositorio LaTeX.
```
