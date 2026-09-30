# Argentina: matriz de producción de gas (2006–2026)

Dashboard interactivo sobre la evolución de la producción de gas natural en Argentina, construido con Google BigQuery y Looker Studio a partir de datos abiertos de la Secretaría de Energía.

🔗 **[Ver dashboard en Looker Studio](https://datastudio.google.com/reporting/cf301dc4-9ae2-439a-b327-3bbab070c847)**

![Dashboard](https://github.com/user-attachments/assets/cc1db1cf-df78-4ed7-afed-72546b24f0ce)

## Pregunta guía
**¿Cómo cambió la matriz de producción de gas y quiénes lideran ese cambio?**

## Hallazgos principales
- **El no convencional superó al convencional en julio de 2021** y hoy explica cerca del 70% de la producción.
- **YPF lidera la producción total** (263,8 MMm3 acumulados) y es, por amplio margen, la principal productora no convencional (87,5 MMm3, frente a 27,6 de Total Austral).
- **Total Austral sigue siendo la mayor productora convencional** (222 MMm3), lo que muestra dos perfiles: empresas que lideran la transición y empresas que sostienen la producción histórica.
- Los KPIs del dashboard (% no convencional sobre el total y variación interanual) permiten filtrar por empresa y período.

## Datos
- Fuente: [Producción de petróleo y gas por pozo – Secretaría de Energía (datos.gob.ar)](https://datos.gob.ar/dataset/produccion-de-petroleo-y-gas-por-pozo)
- Granularidad: mensual, por pozo y empresa. Unidad: MMm3.

## Proceso técnico
1. **Ingesta:** carga de los archivos de la Secretaría de Energía en BigQuery.
2. **Unificación:** `UNION ALL` de todas las tablas en una sola.
3. **Selección de variables:** nueva tabla solo con las columnas relevantes (fecha, empresa, tipo de recurso, producción de gas).
4. **Visualización:** dashboard en Looker Studio con filtros por empresa e intervalo temporal, dos KPIs, serie temporal, tabla con mapa de calor y gráfico de participación no convencional.

## Limitaciones y próximos pasos
- "No convencional" incluye Vaca Muerta pero también otras formaciones; el dataset no permite aislarlas.
- Algunos nombres de empresa aparecen duplicados por razón social (ej. Pan American Energy); queda pendiente normalizarlos.
- Incorporar producción de petróleo.

## Herramientas
BigQuery · SQL · Looker Studio · Desarrollado con asistencia de IA (Gemini) para [completar: qué tareas].

## Autores
Juan Diego Herrera · [LinkedIn](https://www.linkedin.com/in/juan-diego-herrera-b995223a8/) · [GitHub](https://github.com/JuanDiegoHerrera)
Celina Sosa · [LinkedIn](https://linkedin.com/in/celina-sosa-950881220) · [GitHub](https://github.com/EconoCelina)
