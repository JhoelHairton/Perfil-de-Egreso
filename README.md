# HemoScan Andino — Proyecto Integrador (Perfil de Egreso)

Sistema **no invasivo de tamizaje de anemia infantil** con fusión óptica multisensor y
autocalibración por altitud, para el contexto altoandino de Puno (Perú).
Universidad Peruana Unión (UPeU) — Escuela Profesional de Ingeniería de Sistemas, Filial Juliaca.

Este repositorio reúne los documentos del proyecto organizados por **área de competencia**
del perfil de egreso.

---

## 📄 Documentos (PDF)

### Área B — CE01 · Gestión de Tecnologías de Información
| # | Documento |
|---|-----------|
| 01 | Diagnóstico Organizacional y Alineamiento Estratégico |
| 02 | Business Case |
| 03 | Plan de Gestión del Proyecto |
| 04 | Modelado de Procesos AS-IS / TO-BE |

### Área C — CE02 · Ingeniería de Software
| # | Documento |
|---|-----------|
| 05 | Especificación de Requerimientos y Diseño del Sistema |
| 06 | Plataforma de Datos (Parte 1) |
| 11 | **Arquitectura Integrada del Sistema** (vista transversal a las tres áreas) |

### Área A — CE03 · Infraestructura Tecnológica
| # | Documento |
|---|-----------|
| 07 | Diseño de Red |
| 08 | Planificación de Seguridad |
| 09 | Diseño de Centro de Datos |

### Transversales
| # | Documento |
|---|-----------|
| 00 | Documento Consolidado (los 9 entregables en un solo archivo) |
| 10 | Contenido de Sustentación |

---

## 📁 Estructura del repositorio

```
Documentos-PDF/        Documentos finales en PDF, agrupados por área de competencia
Fuentes-LaTeX/         Código fuente LaTeX (.tex) + assets/ (diagramas e imágenes)
```

## 🛠️ Compilar las fuentes

Los documentos se compilan con LaTeX (MiKTeX / TeX Live). Desde `Fuentes-LaTeX/`:

```bash
latexmk -pdf 11-Arquitectura-Integrada.tex
```

Los diagramas incluidos son **imágenes vectoriales** generadas como *diagrama-como-código*
(notación Mermaid) y renderizadas a PDF, ubicadas en `Fuentes-LaTeX/assets/`.

---

## 🧩 Sobre el sistema

- **Dispositivo:** ESP32-S3 + espectrómetro AS7341 (11 canales) + MAX30102 (PPG) + LED de alto CRI.
- **App móvil:** Flutter/PWA *offline-first*, inferencia embebida (ONNX/TFLite) y autocalibración por altitud.
- **Backend:** FastAPI (monolito modular, 7 paquetes de dominio), interoperabilidad HL7 **FHIR**.
- **Datos:** PostgreSQL 16 + PostGIS 3.4 (4 esquemas, 24 tablas); recursos FHIR (Patient, Consent, Device, Observation, Provenance, AuditEvent).
- **Identidad:** Keycloak (OIDC / RBAC). **Web:** React/TypeScript con analítica geoespacial (H3, MapLibre).

> Principio rector: **tamizaje, nunca diagnóstico autónomo** — toda confirmación exige
> supervisión humana (DS 115-2025-PCM, Ley N.° 29733).
