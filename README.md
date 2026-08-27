# Quién paga el cuidado y quién lo absorbe

### La discapacidad como mecanismo silencioso de desigualdad de género en Bogotá

**DataJam Multiuniversitario 2026 — Edición 3**

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cjdotbit/DataJam2026_cuidado_discapacidad_Bogota/blob/main/DataJam2026_cuidado_discapacidad_Bogota.ipynb)

**Universidad de Sucre · Sincelejo-Sucre, Colombia**

</div>
<div align="center">
  <img src="pictures/DataJam-edicion-3-2026.png" alt="LogoDataJam" width="700" />
</div>


**Autores:** María Clareth Méndez Ramos, Jose Carlos Arroyo Cantero & Valentina Terán Barreto

**DashBoard:** Acceso al panel de visualización: [📊 **Ver Dashboard**](https://cjdotbit.github.io/DataJam2026_cuidado_discapacidad_Bogota/dashboard/)

---

##  Descripción

Este proyecto analiza la **carga no remunerada de cuidado asociada a la discapacidad en Bogotá**, con énfasis en su distribución territorial y su marcada feminización.

El análisis busca identificar dónde se concentra la demanda de cuidado derivada de la discapacidad, qué tan feminizado se encuentra este cuidado y qué tan alineada está la oferta territorial del **Sistema Distrital de Cuidado** con dicha demanda.

La pregunta central del proyecto es:

> **¿Dónde se concentra en Bogotá la carga no remunerada de cuidado derivada de la discapacidad, con qué grado de feminización, y qué tan alineada está la oferta territorial del Sistema Distrital de Cuidado con esa carga?**

El análisis utiliza datos públicos y desarrolla un flujo reproducible de descarga, auditoría, depuración, integración y análisis de las fuentes.

---

##  Objetivos

* Identificar la magnitud de la población con discapacidad que requiere ayuda de otra persona.
* Analizar quién asume el cuidado y su distribución por sexo.
* Estudiar cómo cambia la persona cuidadora a lo largo del curso de vida.
* Identificar diferencias territoriales entre las localidades de Bogotá.
* Medir la carga de cuidado y su feminización mediante indicadores comparables.
* Contrastar la demanda territorial de cuidado con la oferta del Sistema Distrital de Cuidado.
* Identificar territorios que podrían requerir una mayor atención institucional.

---

##  Datos

La fuente principal es el registro de **personas con discapacidad certificada en Bogotá D.C.**, publicado por la Secretaría Distrital de Salud a través del Observatorio de Salud de Bogotá.

El registro utilizado contiene **91.455 registros, 53 variables y cubre las vigencias 2020–2026**.

El proyecto integra cinco fuentes públicas provenientes de diferentes entidades distritales:

1. Registro de personas con discapacidad certificada.
2. Información de población por localidad.
3. Información geográfica de las Manzanas del Cuidado.
4. Proyecciones y retroproyecciones de población.
5. Información complementaria utilizada para caracterizar la oferta territorial de cuidado.

Las fuentes son descargadas automáticamente desde sus respectivos servicios públicos durante la ejecución del notebook.

**Importante:** los datasets no se incluyen en este repositorio. El notebook contiene el proceso necesario para obtenerlos.

---

##  Metodología

El análisis se desarrolla en cuatro grandes etapas:

### 1. Preparación y auditoría de datos

Se descargan las fuentes públicas y se realizan procesos de:

* carga y validación;
* normalización;
* depuración;
* integración entre fuentes;
* identificación de localidades;
* control de registros insuficientes;
* trazabilidad de las fuentes utilizadas.

El notebook incorpora mecanismos de descarga con reintentos y una alternativa mediante el catálogo CKAN cuando la descarga directa no está disponible.

### 2. Identificación de la carga de cuidado

Se identifican las personas que declaran requerir ayuda y se caracteriza la persona que presta dicha ayuda.

El análisis distingue, entre otras categorías, cuidadoras familiares mujeres, cuidadores familiares hombres, cuidado remunerado y ausencia de cuidador identificado.

### 3. Construcción de indicadores

Se calculan cuatro indicadores principales:

| Indicador | Significado                                                                                   |
| --------- | --------------------------------------------------------------------------------------------- |
| **IFC**   | Feminización del cuidado: porcentaje de cuidadores familiares que son mujeres                 |
| **CCM**   | Carga de cuidado materno: porcentaje de personas cuidadas por su madre                        |
| **CSR**   | Cuidado sin relevo: porcentaje de personas adultas que continúan siendo cuidadas por su madre |
| **DC**    | Demanda de cuidado: porcentaje de personas certificadas que requieren ayuda                   |

El **CSR (Cuidado sin relevo)** constituye una construcción propia del ejercicio y busca identificar situaciones en las que el relevo generacional del cuidado no se ha producido.

### 4. Correspondencia entre demanda y oferta

Para comparar la demanda de cuidado con la oferta territorial se construye el **Índice de Correspondencia Oferta-Demanda (ICOD)**.

La demanda se expresa mediante la tasa de carga de cuidado por cada 1.000 habitantes, mientras que la oferta se expresa mediante los servicios de cuidado por cada 100.000 habitantes.

El ICOD permite clasificar las localidades en tres situaciones:

* **Prioridad de expansión:** alta demanda relativa y baja oferta relativa.
* **Sostener y monitorear:** oferta proporcional a la demanda.
* **Revisar cobertura o subregistro:** oferta alta frente a la carga registrada.

Las localidades con una base insuficiente de casos se muestran para transparencia, pero no se utilizan para sustentar conclusiones.

---

##  Principales hallazgos

El análisis encuentra una marcada feminización del cuidado.

Entre las personas certificadas que requieren ayuda y cuentan con un cuidador familiar identificado:

* **85,5 %** del cuidado familiar es realizado por mujeres.
* La relación es de aproximadamente **5,9 mujeres cuidadoras por cada hombre cuidador**.
* La madre representa una proporción especialmente importante dentro del cuidado familiar.
* En la adultez, una proporción significativa de personas con discapacidad continúa siendo cuidada por su madre.
* En las personas mayores de 60 años, el cuidado se desplaza principalmente hacia otras mujeres de la familia, especialmente las hijas y esposas.

Estos resultados muestran que el cuidado asociado a la discapacidad no se distribuye de manera equilibrada entre hombres y mujeres y que, a lo largo del curso de vida, existe una transferencia del cuidado entre mujeres de una misma familia.

---

##  Enfoque territorial

El análisis se realiza para las localidades de Bogotá y permite comparar:

* número de personas que requieren ayuda;
* feminización del cuidado;
* cuidado materno;
* cuidado sin relevo;
* demanda relativa de cuidado;
* número de Manzanas del Cuidado;
* servicios disponibles;
* correspondencia entre demanda y oferta.

Para evitar conclusiones basadas en muestras pequeñas, se establece un umbral mínimo de **300 cuidadores por localidad** y un mínimo de **20 casos por combinación de localidad y etapa del curso de vida**.

---

##  Relevancia para la política pública

El proyecto conecta la política de discapacidad con la política distrital de cuidado.

Los resultados pueden utilizarse como insumo para analizar la distribución territorial de la demanda de cuidado y contrastarla con el despliegue del Sistema Distrital de Cuidado.

El ejercicio se articula principalmente con:

* **Plan Distrital de Desarrollo Bogotá Camina Segura 2024–2027**.
* **Política Pública de Discapacidad para Bogotá 2023–2034**.
* **Sistema Distrital de Cuidado**.
* **Política Pública de Mujeres y Equidad de Género**.

La finalidad es pasar de un diagnóstico general sobre la feminización del cuidado a una lectura territorial que pueda contribuir a la priorización de intervenciones.

---

##  Estructura del repositorio

```text
DataJam2026-cuidado-discapacidad-Bogota/
│
├── README.md
├── pictures
├── DataJam2026_cuidado_discapacidad_Bogota.ipynb
└── .gitignore
```

El notebook contiene el proceso completo de análisis, desde la descarga de las fuentes hasta la generación de resultados y tablas.

---

##  Fuentes

* Secretaría Distrital de Salud — Observatorio de Salud de Bogotá: población con discapacidad certificada en Bogotá D.C.
* Datos Abiertos Bogotá — Proyecciones y retroproyecciones de población 2005–2035.
* Datos Abiertos Bogotá — Información territorial de las Manzanas del Cuidado.
* Fuentes públicas distritales utilizadas para población y oferta territorial de cuidado.

---

##  Autores

**María Clareth Méndez Ramos**
**Jose Carlos Arroyo Cantero**
**Valentina Terán Barreto**

**DataJam Multiuniversitario 2026 — Edición 3**
