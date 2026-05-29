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

## 3. Capítulos y anexos

| Archivo | Contenido | Estado |
|---|---|---|
| `section/1_introduction.tex` | Introducción general | Escrito |
| `section/2_requirements-restrictions.tex` | Requerimientos y restricciones | Escrito |
| `section/3_general_design_system.tex` | Diseño general del sistema | [[Placeholder]] |
| `section/4_HW.tex` | Hardware del nodo de sensado | Escrito |
| `section/5_SDR-acquisition.tex` | Software del sensor (SDR) | Escrito |
| `section/6_Platform_cloud.tex` | Plataforma web en la nube | Escrito |
| `section/7_Spectral-localization_cloud.tex` | Análisis espectral y localización | Escrito |
| `section/8_Test_protocols_edge-cloud.tex` | Protocolos de prueba | [[Placeholder]] |
| `section/9_System_integration.tex` | Integración general del sistema | [[Placeholder]] |
| `section/10_General_conclusions.tex` | Conclusiones generales | [[Placeholder]] |
| `section/11_Recommendations.tex` | Recomendaciones | [[Placeholder]] |
| `section/12_References.tex` | Referencias | [[Placeholder]] |
| `section/A_IA-collaboration-technique.tex` | Técnica de desarrollo con agentes IA | Escrito |
| `section/B_Additional_diagrams.tex` | Diagramas adicionales | [[Placeholder]] |
| `section/C_Manuals_guides.tex` | Manuales o guías de uso | [[Placeholder]] |
| `section/D_Test_results.tex` | Resultados de pruebas | [[Placeholder]] |

---

## 4. Cómo compilar

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

## 10. Criterio de calidad

Un capítulo está listo si una persona externa al desarrollo puede leerlo y entender:
qué componente se documenta, cómo se conecta con el sistema, cómo funciona, qué decisiones se tomaron, qué problemas aparecieron, qué ajustes se aplicaron, qué evidencia respalda el resultado, qué aprendió el equipo y qué queda pendiente.
