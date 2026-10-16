# 🛠️ Cómo Armar el Repositorio del Proyecto con el Cliente Real

Esta guía es para el **equipo**, no para un taller específico: explica cómo organizar en un solo repositorio de GitHub todo el trabajo de la Parte 2 ("Aplicación al Cliente Real") de los 10 talleres del curso, de modo que el resultado final sea algo que **el cliente pueda usar**, no solo una carpeta de entregables académicos.

---

## 1. Dos audiencias, un repositorio

El repositorio de su proyecto lo van a leer dos tipos de personas muy distintas:

- **El área de negocio del cliente** — quiere entender rápido cuál era el problema, qué se propone y cómo se implementa. No necesita (ni quiere) leer 10 informes técnicos para llegar a esa respuesta.
- **El docente y ustedes mismos** — necesitan ver el detalle completo, taller por taller, para verificar la trazabilidad y el rigor del análisis.

Por eso el repositorio tiene una estructura de dos capas: un **README raíz liviano y de negocio** en la puerta de entrada, y el detalle técnico organizado por carpetas debajo, para quien quiera profundizar. Nadie del área de negocio debería tener que abrir la carpeta `05-seguridad-stride/` para entender qué se les está proponiendo — para eso está el resumen ejecutivo.

---

## 2. Un repositorio por equipo, con una carpeta por taller

Cada equipo crea **un solo repositorio** (no diez) para su cliente real, nombrado así: `AREM-EquipoX-NombreCliente` (ej. `AREM-Equipo3-FundacionSaludViva`). Dentro, una carpeta por taller — solo con lo de la Parte 2 (Aplicación al Cliente Real); lo de la Parte 1 (caso de clase) se queda en los repos de taller, no aquí.

```text
AREM-EquipoX-NombreCliente/
├── README.md                          # ⭐ Punto de entrada — ver plantilla en este repo
├── resumen-ejecutivo.md               # Copia del Taller 9 — lo primero que debe leer el cliente
├── 00-preliminary-vision/
│   ├── ficha-caracterizacion.md
│   ├── vision.md
│   └── referencias.md
├── 01-bpmn/
│   ├── modelo-final.drawio
│   ├── informe.md
│   └── referencias.md
├── 02-modelo-informacion/
│   ├── modelo-final-er.drawio
│   ├── diagrama-contexto-final.drawio
│   ├── informe.md
│   └── referencias.md
├── 03-arquitectura-c4/
│   ├── c1-contexto-final.drawio
│   ├── c2-contenedores-final.drawio
│   ├── informe.md
│   └── referencias.md
├── 04-infraestructura/
│   ├── mapa-final.drawio
│   ├── informe.md
│   └── referencias.md
├── 05-seguridad-stride/
│   ├── tabla-stride-cliente.xlsx
│   ├── informe.md
│   └── referencias.md
├── 06-normatividad/
│   ├── checklist-cliente.xlsx
│   ├── informe.md
│   └── referencias.md
├── 07-opportunities-solutions/
│   ├── mejora-arquitectura.md         # Documento principal del Taller 7 (máx. 6 páginas + anexos)
│   ├── EquipoX_Mejora_Arquitectura.pdf # El mismo documento en PDF (obligatorio)
│   ├── to-be-proceso.drawio           # Proceso mejorado (BPMN)
│   ├── matriz-decision.md
│   ├── to-be-aplicaciones-final.drawio
│   ├── to-be-tecnologia-final.drawio
│   ├── matriz-brechas.xlsx
│   └── referencias.md
├── 08-integracion-vistas/
│   ├── tablero-integrado-cliente.drawio
│   ├── informe.md
│   └── referencias.md
└── 09-presentacion-final/
    ├── presentacion.pdf
    ├── matriz-riesgos.xlsx
    ├── plan-implementacion.md
    ├── plan-gobernanza.md
    ├── procedimiento-cambios.md
    ├── retroalimentacion-cliente.md   # Firmada por el cliente (o PDF escaneado)
    ├── vistas-finales/
    │   ├── archimate-motivacion.(archimate|drawio) + .png
    │   └── archimate-migracion.(archimate|drawio) + .png
    └── reflexiones/
```

La coevaluación **no** va en el repositorio: cada integrante la envía privada por el Aula Virtual (ver Taller 9).

Cada carpeta usa las plantillas del repo del taller correspondiente — cópielas de `plantillas/` de cada `AREM-Taller_N_...` a la carpeta de aquí y llénelas con el trabajo del cliente real.

---

## 3. Cómo fluye la información entre carpetas (trazabilidad)

Cada carpeta no es un ejercicio aislado: usa lo que produjo la anterior. Si dos carpetas se contradicen, algo quedó mal — revisen esta tabla antes de dar por cerrado un corte.

| De → A | Qué se traslada |
|---|---|
| 00 → 01 | Un proceso de "Procesos clave del negocio" de la Ficha se convierte en el proceso a modelar en BPMN |
| 00 → 02 | El contexto del negocio (sistemas y actores mencionados en la Ficha) informa el ERD y el diagrama de contexto |
| 01, 02 → 03 | Los procesos y entidades ya modelados delimitan qué sistema se documenta en C1/C2 |
| 03 → 04 | Los contenedores del C2 aparecen como componentes en el mapa de infraestructura |
| 03, 04 → 05 | Los componentes y flujos de C4/infraestructura son el objeto del análisis STRIDE |
| 00, 02 → 06 | Los datos sensibles identificados en la Ficha y el ERD se evalúan contra el checklist normativo |
| 03, 04, 05, 06 → 07 | Los riesgos y brechas de C4, infraestructura, STRIDE y normatividad se consolidan en el TO-BE |
| 00–07 → 08 | Todas las vistas (AS-IS y TO-BE) se integran en un solo tablero coherente |
| 00–08 → 09 | Todo se condensa en la narrativa de 4 actos, el plan de implementación, la gobernanza y el resumen ejecutivo |

---

## 4. Cronograma del semestre (confirmado)

El curso se dicta los sábados. Con el Taller 7 (Opportunities & Solutions) insertado entre Normatividad y Presentación Final, el mapeo original del enunciado ("Corte 2 = Aplicaciones + Tecnológica + Opportunities & Solutions") se recalibró así: el TO-BE (07) se corrió después de Seguridad (05) y Normatividad (06), porque necesita las brechas de ambos para tener sentido. Calendario confirmado 2026-II:

| # | Sábado | Taller / actividad |
|---|---|---|
| 1 | 25/07 | Taller 0 — Preliminary y Architecture Vision |
| 2 | 01/08 | Taller 1 — BPMN |
| 3 | 08/08 | Taller 2 — Modelo de Información |
| 4 | 15/08 | Cierre y ajustes Corte 1 |
| 5 | 22/08 | 🟢 **Sustentación Corte 1** (`00`, `01`, `02`) |
| 6 | 29/08 | Taller 3 — Arquitectura C4 |
| 7 | 05/09 | Taller 4 — Infraestructura |
| 8 | 12/09 | Taller 5 — STRIDE |
| 9 | 19/09 | Taller 6 — Normatividad |
| 10 | 26/09 | Cierre y ajustes Corte 2 |
| 11 | 03/10 | 🟢 **Sustentación Corte 2** (`03`, `04`, `05`, `06`) |
| 12 | 10/10 | Taller 7 — Opportunities & Solutions |
| — | ~~17/10~~ | Semana de receso — sin clase |
| 13 | 24/10 | Taller 8 — Integración de Vistas + método de análisis de riesgos (insumo de la matriz de riesgos del Taller 9) |
| 14 | 31/10 | Taller 9 — Presentación Final (preparación): plan de implementación con gestión del cambio, gobernanza con métricas, ADR y vistas ArchiMate |
| 15 | 07/11 | Cierre Corte 3 / Ensayo |
| 16 | 14/11 | 🟢 **Presentación Final con el cliente/negocio** (`07`, `08`, `09`) — el cliente debe asistir (presencial o virtual) |
| — | Mar 17/11 | Plazo del paquete final ajustado con la retroalimentación del panel (repositorio completo + retroalimentación del cliente firmada + coevaluación por Aula Virtual) |

Cada corte queda con al menos un sábado libre de contenido nuevo antes de sustentar (15/08, 26/09). El cierre final queda con un solo sábado de colchón (07/11) en vez de dos, porque el 17/10 no hay clase — sigue alcanzando para los 3 talleres restantes sin romper el orden de dependencias, pero ya sin margen extra: si se corre otra fecha en esta ventana, revisar de nuevo.

### 4.1 Qué presentación corresponde a cada taller

Los decks de clase se numeran por módulo y los repositorios por taller, y la numeración no coincide uno a uno: desde el Módulo 4 hay un desfase de uno, y al final se cruzan (el módulo de Riesgos se dicta con el Taller 8 y el de Gobierno con el Taller 9). Esta tabla dice qué archivo abrir en cada repositorio de taller:

| Taller | Módulo de la presentación | Archivo pptx (en el repo del taller) |
|---|---|---|
| Taller 0 | Módulo 0 (logística del curso) y Módulo 1 (Arquitectura Empresarial: capas, TOGAF ADM, Zachman) | `0. Introduccion - Arquitectura Empresarial.pptx` y `1. Arquitectura Empresarial.pptx` |
| Taller 1 | Módulo 2: Modelado de procesos (BPMN) | `2. PMN_Modelado_Procesos_v2.pptx` |
| Taller 2 | Módulo 3: Modelado de información (ERD) | `3. Modelado_Informacion_ERD_v2.pptx` |
| Taller 3 | Módulo 4: Documentar la arquitectura de software (C4) | `4. Documentar_arquitectura_software_v2.pptx` |
| Taller 4 | Módulo 5: Infraestructura y topologías | `5. Infraestructura_Topologias.pptx` |
| Taller 5 | Módulo 6: Seguridad arquitectónica y STRIDE | `6. Seguridad_STRIDE_unificado.pptx` |
| Taller 6 | Módulo 7: Normatividad y cumplimiento | `7. Normatividad_Cumplimiento.pptx` |
| Taller 7 | Deck del Taller 7: Oportunidades y soluciones | `7. Oportunidades_Soluciones.pptx` |
| Taller 8 | Módulo 9: Evaluación de riesgos arquitectónicos | `9. Riesgos_Arquitectonicos_unificado.pptx` |
| Taller 9 | Módulo 8: Gobierno de arquitectura | `8. Gobierno_Arquitectura.pptx` |

---

## 5. Cómo compartir el repositorio

- Agregue al docente como colaborador del repositorio, o déjelo público (igual que los repos de taller).
- Comparta el link por el canal que ya usa el curso (Aula Virtual / correo) — no hace falta una organización de GitHub aparte.

---

## 6. Plantilla del README raíz (la puerta de entrada para el cliente)

Copie [`plantilla_readme_equipo.md`](plantilla_readme_equipo.md) como `README.md` en la raíz de su repositorio y complétela. Es lo primero — y para muchos lectores del área de negocio, lo único — que van a leer.

---

## ✅ Licencia

Este repositorio es de uso académico bajo licencia MIT. Hace parte del curso de Arquitectura Empresarial - Universidad de La Sabana.
