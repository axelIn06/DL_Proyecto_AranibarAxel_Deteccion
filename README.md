# Detección de objetos en COCO128 con YOLOv8

## Ruta elegida y dataset
Este proyecto sigue la **ruta de detección de objetos** utilizando la arquitectura **YOLOv8** en tres variantes: **nano (YOLOv8n), small (YOLOv8s) y medium (YOLOv8m)**.  

El dataset utilizado es **COCO128**, un subconjunto reducido del dataset COCO oficial, compuesto por 128 imágenes anotadas en formato YOLO y distribuidas en 80 clases.  
- Fuente: [COCO128 - Ultralytics](https://github.com/ultralytics/yolov5/releases/download/v1.0/coco128.zip)  
- Licencia: MIT License (uso libre para investigación y desarrollo).  

---

## Cómo ejecutar
El proyecto está diseñado para ejecutarse en **Google Colab** o en un entorno local con soporte de **Jupyter Notebook**.  

1. Abrir el notebook en Colab o Jupyter.  
2. En el caso de Colab:  
   - Ir a `Entorno de ejecución > Cambiar tipo de entorno de ejecución`.  
   - Seleccionar **GPU** como acelerador de hardware.  
3. Montar Google Drive si se desea guardar resultados de entrenamiento (`/content/drive`).  

---

## Cómo entrenar y evaluar
El notebook está dividido en secciones con celdas que deben ejecutarse en orden:  

1. **Instalación de dependencias**  
   - Ejecutar la celda que instala `ultralytics` y las librerías necesarias.  

2. **Carga del dataset**  
   - Ejecutar la celda que descarga y descomprime **COCO128**.  
   - Verificar la estructura de carpetas `train`, `val` y `test`.  

3. **Entrenamiento de modelos**  
   - Para cada variante (YOLOv8n, YOLOv8s, YOLOv8m), ejecutar la celda correspondiente al entrenamiento.  
   - Cada entrenamiento se realiza por **20 épocas** con las mismas condiciones.  

4. **Evaluación de resultados**  
   - Al finalizar cada entrenamiento, ejecutar la celda de **validación**, que genera métricas como `mAP@0.5`, `mAP@[.5:.95]`, precisión, recall y velocidad de inferencia.  

5. **Inferencia en imágenes de prueba**  
   - Ejecutar la celda de inferencia para generar predicciones sobre 3–5 imágenes del conjunto de prueba y guardar las salidas en la carpeta `results/figures/`.  

---

## Cómo generar la tabla y el gráfico de métricas
1. **Tabla comparativa**  
   - Ejecutar la celda que consolida los resultados de cada modelo en un **DataFrame de Pandas**.  
   - La tabla final incluye métricas clave: `mAP@0.5`, `mAP@[.5:.95]`, precisión, recall y velocidad de inferencia.  

2. **Gráfico de métricas comparativas**  
   - Ejecutar la celda de visualización, que genera gráficos comparando el rendimiento de los tres modelos.  
   - Los gráficos incluyen:  
     - Barras comparativas por métrica.  
     - Curva de precisión vs velocidad.  
   - Los resultados se guardan automáticamente en la carpeta `results/figures/`.  

---

