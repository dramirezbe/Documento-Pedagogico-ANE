# AGENTS.md — Documento Pedagógico ANE

## Build

```bash
latexmk -pdf main.tex     # compila (auto-reruns para TOC/referencias)
latexmk -pdf -c           # limpia auxiliares (.aux, .toc, .log, .out)
```

`latexmk` maneja los pases múltiples automáticamente. No usar `pdflatex` manual.

## Encoding

UTF-8 directo (`\usepackage[utf8]{inputenc}` + `\usepackage[T1]{fontenc}`).

**Usar caracteres Unicode reales (á, é, í, ó, ú, ñ), NUNCA escapes tipo `\'a`.**
Lo mismo para `\~n` → `ñ`. Si aparecen escapes de acentos, reemplazarlos.

Unicode no permitido: caracteres CJK (`正`, `式`), math chars (`−` U+2212, `≤` U+2264). Usar `$-$`, `$\leq$`.

## Estructura

```
main.tex          ← maestro, solo editar para añadir/quitar \inputchapter
section/*.tex     ← un archivo por capítulo, cada autor edita solo el suyo
section/img/      ← imágenes por carpeta: cap04_hw/, cap05_sdr/, etc.
```

`\inputchapter{section/archivo}` carga con fallback si el archivo no existe.

## Placeholders (10 de 16 archivos)

Los siguientes capítulos **no tienen contenido real**, solo estructura con `[[Placeholder]]`:

2, 3, 8, 9, 10, 11, 12, B, C, D

Reconocibles por la marca `[[Placeholder]]` en cada sección.

Los que SÍ tienen contenido real: 1 (Introducción), 4 (HW), 5 (SDR), 6 (Plataforma cloud), 7 (Análisis espectral), Anexo A (IA).

## Capítulo 7 — gotchas específicas

El capítulo 7 es el más complejo y ya fue corregido. Lecciones para no repetir:

- **Tablas**: usar `{@{}l X@{}}` o `{@{}p{Xcm} p{Ycm} X@{}}`. NUNCA `{@{}l l X@{}}` si las filas solo tienen 2 columnas.
- **Secciones**: NO poner `\textbf{}` ni `\emph{}` dentro de `\section{}`, `\subsection{}`, `\subsubsection{}`. Causa negrita/cursiva en el índice (TOC).
- No incluir `\end{document}` en archivos `\input`-eados.
- No usar `\=` como signo igual (es acento macron en LaTeX). Usar `=` directo.
- Fórmulas de reglas en celdas de tabla: usar modo matemático `$...$`.

## Comandos personalizados (definidos en main.tex)

| Comando | Uso |
|---------|-----|
| `\pendiente{texto}` | Marca texto pendiente en rojo. Eliminar antes de versión final |
| `\inputchapter{path}` | Incluye capítulo con fallback si no existe |
| `\softwareRepo{...}{...}...` | Tabla estándar de repositorio (8 argumentos) |
| `\problemTableTemplate` | Tabla larga de problemas/decisiones/ajustes |
| `\testTableTemplate` | Matriz de pruebas |
| `\knowledgeTransferTableTemplate` | Tabla de aprendizajes |

## Tablas

Usar `booktabs` + `tabularx`. Estructura canónica:

```latex
\begin{tabularx}{\textwidth}{@{}l X@{}}
\toprule
Col1 & Col2 \\
\midrule
dato & descripción \\
\bottomrule
\end{tabularx}
```

- Las filas de datos deben terminar con `\\` (doble backslash).
- `\toprule`, `\midrule`, `\bottomrule` NO llevan `\\`.
- Si una celda larga se sale de página, cambiar `l` por `p{Xcm}`.

## Figuras

Usar `[H]` (float package), `\includegraphics`, `\caption`, `\label`. Rutas relativas desde raíz:

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.85\textwidth]{section/img/cap04_hw/rpi5.png}
    \caption{Descripción. Fuente: elaboración propia.}
    \label{fig:rpi5}
\end{figure}
```

## Convenciones

- Idioma: español (`\usepackage[spanish,es-tabla]{babel}`)
- Report class, 12pt, letterpaper, margen izquierdo 3cm
- No incluir código fuente largo. Solo fragmentos cortos o pseudocódigo.
- Referencias a repositorios: usar `\softwareRepo` o enlace `\url{}`. Si no existe: "Repositorio pendiente de publicación."
