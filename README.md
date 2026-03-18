# Automated Receipt Analytics Pipeline

> Transforming unstructured receipts into structured, analytics-ready data using AI and data engineering principles.

---

## 🚀 Key Highlights

- 📄 Automated extraction from real-world receipts (Telegram ingestion)
- 🧠 LLM-powered structured data interpretation (not just OCR)
- 📊 Line-item level granularity for real analytics
- ⚙️ End-to-end pipeline (ingestion → processing → BI dashboard)
- 📈 Designed for decision-making, not just data collection

---

## 🧰 Tech Stack

**Automation:** n8n, Telegram Bot API  
**AI Processing:** OpenAI, LlamaIndex  
**Data Modeling:** JSON Schema Validation  
**Storage:** Google Sheets  
**Visualization:** Power BI  


## 📄 Telegram Demo

![Telegram Demo](./images/telegram_demo.jpg)

---

## 🖼 Full Workflow

![Workflow Overview](./images/workflow_overview.jpg)

---

## 📊 Dashboard Preview

![Dashboard Preview](./images/dashboard_preview.jpg)

---

## 📊 Tooltip Preview

![Dashboard Tooltip Preview](./images/dashboard_tooltip_preview.jpg)

---
# Automated Receipt Analytics Pipeline
## 🌐 Table of Contents

### 🇺🇸 English Version

### 🇪🇸 Versión en Español

### 👤 Author

## 🇺🇸 English Version
# 📌 Project Overview

Most expense tracking systems fail not because of lack of tools, but because the data itself is messy, inconsistent, and expensive to process.

This project was built to solve that core problem: transforming unstructured financial documents into reliable, analytics-ready datasets — automatically.

Instead of focusing only on extraction, the pipeline is designed around a key analytical principle:

Data is only valuable when it is structured, consistent, and decision-ready.

🧠 Analytical Motivation (Personal Trigger)

This project originates from a personal problem:

I was spending money, but I didn’t truly understand how that spending was composed.

Traditional tracking methods only provided high-level summaries, which were not enough to support real decision-making.

I needed to move from:

“How much am I spending?”
to:

“What exactly am I spending on, and where can I optimize?”

The limitation was clear:
receipts contain the real data — but they are not usable as-is.

❓ Key Questions This Project Answers
Level 1 — Visibility

How much am I actually spending over time?

Where is most of my money going?

Level 2 — Composition

Which products or categories explain most of my expenses?

How is each purchase internally distributed?

Level 3 — Behavior

What consumption patterns do I have?

Am I repeating unnecessary purchases?

Level 4 — Optimization

Where can I reduce spending without impacting my lifestyle?

What decisions could I make if I had better data?

🎯 Business Problem

In real-world scenarios, expense tracking breaks down at the data ingestion layer.

Receipts and invoices:

vary in format

contain ambiguous fields (discounts, totals, taxes)

require manual interpretation

This leads to:

fragmented financial visibility

unreliable reporting

high operational overhead

The real problem is not dashboards — it's data quality.

🧠 Solution Approach

Instead of treating this as a simple OCR problem, the solution is designed as a data pipeline with validation and normalization layers.

Key design decisions:

Use LLMs for structured interpretation, not just extraction

Enforce JSON schema validation to improve reliability

Normalize data at line-item level (critical for analysis)

Prioritize decision-ready data over raw completeness

🔬 Key Differentiator: Granularity

Instead of stopping at total receipt values, the system captures:

product-level data

quantities

unit prices

discounts

This enables:

Pareto analysis

spending optimization

behavioral insights

Without granularity, there is no real analytics — only summaries.

🏗 System Architecture
Telegram Bot
↓
Document Ingestion
↓
Parsing API (Async Processing)
↓
LLM Structured Extraction
↓
Data Normalization Layer
↓
Storage (Analytics-ready)
↓
Power BI Dashboard
🔄 Data Pipeline Logic
1. Ingestion

User sends receipt via Telegram

System captures the document

2. Structuring

Parsing API extracts raw content

LLM converts it into structured JSON

Schema validation ensures consistency

3. Standardization

Line items are normalized

Discounts are reconciled

Data becomes analysis-ready

🧰 Tech Stack

Automation & Orchestration

n8n

Telegram Bot API

AI & Processing

LlamaIndex Parsing API

OpenAI LLM

JSON Schema Validation

Storage

Google Sheets

Analytics

Power BI

📊 Data Structure Example
{
  "Fecha": "DD-MM-YYYY",
  "Lugar": "Merchant Name",
  "MetodoDePago": "Payment Method",
  "Items": [
    {
      "Producto": "Item Name",
      "Cantidad": 1,
      "PrecioUnitario": 100,
      "Descuento": null,
      "Subtotal": 100
    }
  ]
}
⚙ Key Challenges & Insights

Semi-structured documents require interpretation, not extraction

LLM outputs must be constrained to ensure reliability

Discounts and totals often lack explicit mapping

Data modeling defines analytical value

The quality of insights depends on the structure of the data.

🚀 Future Improvements

Migration to SQL-based storage

Automated validation layer

AI-based expense categorization

Real-time analytics

## 🇪🇸 Versión en Español
📌 Descripción del Proyecto

La mayoría de los sistemas de control de gastos fallan no por falta de herramientas, sino porque los datos son inconsistentes, desordenados y difíciles de procesar.

Este proyecto busca resolver ese problema desde la base: transformar documentos financieros no estructurados en datos confiables y listos para análisis de forma automática.

En lugar de enfocarse solo en la extracción, el pipeline se diseña bajo un principio clave:

Los datos solo tienen valor cuando son consistentes, estructurados y utilizables para la toma de decisiones.

🧠 Motivación Analítica (Problema Personal)

Este proyecto nace de una necesidad concreta:

Estaba gastando dinero, pero no entendía realmente cómo se componía ese gasto.

Los métodos tradicionales solo mostraban totales, lo cual no era suficiente para tomar decisiones reales.

Necesitaba pasar de:

“¿Cuánto gasto?”
a:

“¿En qué gasto exactamente y dónde puedo optimizar?”

La limitación era clara:
los tickets contienen la información real, pero no están listos para ser analizados.

❓ Preguntas que Responde el Proyecto
Nivel 1 — Visibilidad

¿Cuánto gasto realmente en el tiempo?

¿Dónde se concentra la mayor parte de mi gasto?

Nivel 2 — Composición

¿Qué productos o categorías explican mi gasto?

¿Cómo se distribuye cada compra internamente?

Nivel 3 — Comportamiento

¿Qué patrones de consumo tengo?

¿Estoy repitiendo compras innecesarias?

Nivel 4 — Optimización

¿Dónde puedo reducir gasto sin afectar mi consumo?

¿Qué decisiones tomaría si tuviera mejor información?

🎯 Problema de Negocio

En la práctica, el problema del seguimiento de gastos aparece en la capa de ingesta de datos.

Los tickets y facturas:

tienen formatos variables

contienen información ambigua

requieren interpretación manual

Esto genera:

baja visibilidad financiera

reportes poco confiables

alto esfuerzo operativo

El problema real no es la visualización, sino la calidad de los datos.

🧠 Enfoque de Solución

Se plantea como un pipeline de datos con validación y normalización, no como un simple OCR.

Decisiones clave:

Uso de LLMs para interpretación estructurada

Validación mediante JSON Schema

Normalización a nivel de ítems

Prioridad en datos listos para análisis

🔬 Diferencial: Granularidad

El sistema trabaja a nivel de detalle:

productos

cantidades

precios unitarios

descuentos

Esto permite análisis reales:

Pareto

optimización de gasto

insights de comportamiento

Sin granularidad, no hay análisis — solo resúmenes.

🏗 Arquitectura
Telegram Bot
↓
Ingesta de documentos
↓
API de parsing
↓
Extracción estructurada con LLM
↓
Normalización
↓
Almacenamiento
↓
Power BI
🔄 Lógica del Pipeline
1. Ingesta

Recepción del ticket

Captura del documento

2. Estructuración

Parsing del contenido

Transformación a JSON

Validación

3. Estandarización

Normalización de ítems

Ajuste de descuentos

Preparación para análisis

🧰 Stack Tecnológico

Automatización

n8n

Telegram Bot API

IA y Procesamiento

LlamaIndex

OpenAI

JSON Schema

Almacenamiento

Google Sheets

Visualización

Power BI

📊 Estructura de Datos
{
  "Fecha": "DD-MM-YYYY",
  "Lugar": "Comercio",
  "MetodoDePago": "Método de pago",
  "Items": [
    {
      "Producto": "Nombre",
      "Cantidad": 1,
      "PrecioUnitario": 100,
      "Descuento": null,
      "Subtotal": 100
    }
  ]
}
⚙ Desafíos y Aprendizajes

Los documentos requieren interpretación

La IA necesita validación estructural

La normalización define el valor del análisis

La calidad del análisis depende de la estructura de los datos.

🚀 Mejoras Futuras

Migración a SQL

Validación automática

Clasificación de gastos

Analítica en tiempo real

👤 Author

Federico Almonacid
Business Intelligence & Data Analytics

📧 federicoalmonacid.laboral@gmail.com

📱 +54 9 2964 628695
🔗 LinkedIn:
https://www.linkedin.com/in/federico-almonacid-a90bb9181/
