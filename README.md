# Proyecto Final: Consumo de Energía y Agua de Modelos de IA (2025)

Análisis del consumo energético e hídrico de 34 modelos de IA generativa usando el dataset público ML.ENERGY Benchmark v3.

## Autores
- Samuel Alvarado Currea
- Natalia Castiblanco
- Ángel Velásquez
- Sofia Lorena Pinzon Suarez

Curso: Data Experience
Facultad: Ingeniería
Año: 2026

## Pregunta principal
¿Cuántos kWh de energía y litros de agua consumieron los modelos de IA en 2025?

## Fuente de datos
Dataset ML.ENERGY Benchmark v3 de la Universidad de Michigan, disponible en Hugging Face (ml-energy/benchmark-v3).

- 838 corridas
- 34 modelos
- 2 GPUs (NVIDIA H100 y B200)
- 5 tareas de benchmark

## Contenido del repositorio
- ProyectoFinal_G7.ipynb - Cuaderno con todo el código y análisis
- Informe_Final.pdf - Informe escrito del proyecto
- Presentacion.pdf - Diapositivas de la sustentación

## Cómo ejecutar el código
1. Abre el notebook en Google Colab.
2. Ejecuta la primera celda para instalar dependencias.
3. Configura tu token de Hugging Face como HF_TOKEN.
4. Ejecuta todas las celdas en orden.

## Resultados principales
- Energía total: 266.56 kWh
- Agua total estimada: 287.88 litros
- GPU con mayor consumo: B200 (164.35 kWh)
- Tarea más consumidora: gpqa (107.64 kWh)
- Modelo de mayor consumo: Qwen 3 235B A22B Thinking FP8 (39.06 kWh)
