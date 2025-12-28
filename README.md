# st 0.8.5 – Custom build

Este repositorio contiene mi build personalizada de **st (simple terminal) 0.8.5**,
con parches aplicados y configuraciones propias.

El objetivo es mantener:
- la versión base estable (`0.8.5`)
- los parches documentados
- una configuración clara y reproducible

---

## Versión

- **st**: 0.8.5
- **Base**: upstream suckless
- **Branch activa**: `master`

---

## Patches aplicados

Los parches originales se guardan en el directorio `patches/`.

### ✔ alpha
- Agrega **transparencia** al fondo de la terminal
- El nivel de opacidad se configura desde `config.h`
- Requiere un compositor (ej: `picom`)
- Patch: `alpha.diff`

---

### ✔ anysize
- Permite **redimensionar la ventana libremente**
- Evita que st fuerce el tamaño a múltiplos exactos de la fuente
- Útil al trabajar con window managers tiling
- Patch: `anysize.diff`

---

### ✔ boxdraw
- Mejora el renderizado de **caracteres box-drawing**
- Corrige líneas y bordes en interfaces TUI
- Esencial para:
  - `htop`
  - `neovim`
  - `tmux`
- Patch: `boxdraw.diff`

---

### ✔ dracula
- Aplica el **tema Dracula** a st
- Colores oscuros y buen contraste
- Ideal para sesiones largas de trabajo
- Patch: `dracula.diff`

---

### ✔ font2
- Permite definir una **fuente secundaria (fallback)**
- Útil para:
  - glyphs de Nerd Fonts
  - símbolos Unicode
- Patch: `font2.diff`

---

### ✔ scrollback
- Agrega **scrollback real** al historial de la terminal
- Permite:
  - scroll con el mouse
  - Shift + PageUp / PageDown
  - revisar salida antigua de comandos
- Patch: `scrolback.diff`

---

## Estructura del repositorio

```text
.
├── st.c
├── config.def.h
├── config.h
├── patches/
│   ├── alpha.diff
│   ├── anysize.diff
│   ├── boxdraw.diff
│   ├── dracula.diff
│   ├── font2.diff
│   └── scrolback.diff
└── README.md

