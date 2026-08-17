# Taller Semana 3 - Grupo 3

## Descripción

Este proyecto presenta una propuesta de rediseño de un flujo analítico
reproducible para integrar información procedente de diferentes fuentes.

El ejercicio consolida las entregas provenientes de los campus Matriz y
Extensión y posteriormente las integra con el catálogo maestro de estudiantes.

El flujo incorpora controles sobre archivos, columnas, duplicados, claves,
fechas, valores nulos y dimensiones de salida.

## Estructura del proyecto

Taller_Sem3_G3/
├── datos/
│   ├── originales/
│   └── procesados/
├── notebooks/
├── scripts/
├── reportes/
├── visualizaciones/
├── documentacion/
├── taller_sem3_g3.ipynb
├── requirements.txt
├── .gitignore
└── README.md

## Archivos originales requeridos

Los siguientes archivos deben colocarse manualmente en:

datos/originales/

- estudiantes_master.xlsx (este archivo estaba corrupto para la apertura desde la descarga; por lo que para su gestion se modifico a csv la extension para postriormente, retornar y grabarlo como xlsx)
- entregas_campus_matriz.csv
- entregas_campus_extension.csv

Los archivos originales no se almacenan en el repositorio remoto.

## Flujo analítico

1. Creación y validación de la estructura del proyecto.
2. Lectura e inspección de las fuentes.
3. Identificación del campus de procedencia.
4. Consolidación de entregas mediante concat.
5. Conversión y validación de fechas.
6. Validación de claves del catálogo maestro.
7. Integración relacional mediante left merge.
8. Identificación de claves sin correspondencia.
9. Control de valores nulos críticos.
10. Generación y exportación de resultados.

## Resultados de control

El proceso identificó:

- 3 archivos fuente procesados.
- 300 registros de entregas.
- 0 duplicados exactos.
- 5 entregas sin correspondencia en el catálogo maestro.
- 9 valores nulos críticos en puntaje_obtenido.
- 0 fechas con errores de conversión.
- 300 registros en el dataset consolidado.

No se descartaron registros durante la integración para conservar la
trazabilidad de las anomalías encontradas.

## Archivos generados

- datos/procesados/entregas_consolidadas.csv
- reportes/claves_sin_correspondencia.csv
- reportes/reporte_control.parquet

## Reproducibilidad

Las dependencias necesarias se encuentran documentadas en
requirements.txt.

El flujo debe ejecutarse de manera secuencial desde el Bloque 1 hasta
el Bloque 5 del notebook taller_sem3_g3.ipynb.