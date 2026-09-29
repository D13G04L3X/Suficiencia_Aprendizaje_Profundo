# Suficiencia – Introducción al Aprendizaje Profundo

Repositorio del proceso de suficiencia de la asignatura **Introducción al Aprendizaje Profundo** (Institución Universitaria ITM).

- **Estudiante:** Diego Alexander Valencia Calderón
- **Docente:** Kevin Osorno Castillo

| Fase | Componente | Dataset | Entrega |
|---|---|---|---|
| Fase 1 (60 %) | Taller 1 – Redes Neuronales Profundas (MLP) | MNIST | 23 oct 2026 |
| Fase 1 (60 %) | Taller 2 – CNN, Transfer Learning y Data Augmentation | Oxford-IIIT Pet (clasificación de razas) | 23 oct 2026 |
| Fase 2 (40 %) | Proyecto final – Segmentación de imágenes (U-Net) | Oxford-IIIT Pet (máscaras trimap) | 25 nov 2026 |

> Los datasets están sujetos a aprobación del docente.

## Estructura del repositorio

```
Suficiencia_Aprendizaje_Profundo/
├── README.md
├── requirements.txt
├── docs/                          Propuesta y documentos de apoyo
├── taller1_mlp/
│   ├── taller1_redes_neuronales_profundas.ipynb
│   ├── figuras/                   EDA, curvas, matriz de confusión, errores
│   ├── resultados/                Métricas exportadas (CSV/JSON)
│   └── modelos/                   Modelo final entrenado (.keras)
├── taller2_cnn_tl_da/
│   ├── taller2_cnn_tl_da.ipynb
│   ├── figuras/
│   ├── resultados/                Tabla comparativa de experimentos
│   └── modelos/
└── proyecto_final/
    ├── proyecto_fase2_segmentacion.ipynb
    ├── figuras/
    ├── resultados/
    ├── modelos/
    ├── informe_tecnico/
    └── presentacion/
```

## Instrucciones de ejecución

### Opción recomendada: Google Colab

1. Abrir el notebook deseado en Google Colab.
2. Activar la GPU: **Entorno de ejecución → Cambiar tipo de entorno de ejecución → GPU (T4)**.
3. Ejecutar todas las celdas: **Entorno de ejecución → Ejecutar todas**.

La primera celda de cada notebook monta Google Drive y localiza el repositorio en:

```
/content/drive/MyDrive/Introducción al aprendizaje profundo/Suficiencia_Aprendizaje_Profundo
```

Si el repositorio se clona en otra ubicación, basta con modificar la variable `REPO_DIR` de esa celda.

Los datasets se descargan automáticamente mediante `keras.datasets` y `tensorflow_datasets`; no se requiere descarga manual.

### Opción local

```bash
python -m venv .venv
.venv\Scripts\activate          # Windows
pip install -r requirements.txt
jupyter notebook
```

Ejecutar cada notebook desde su propia carpeta. Sin GPU, el Taller 2 y el proyecto final pueden tardar considerablemente.

## Datasets

- **MNIST** – LeCun, Cortes y Burges. Cargado con `tf.keras.datasets.mnist`.
- **Oxford-IIIT Pet** – Parkhi, Vedaldi, Zisserman y Jawahar (2012). Licencia CC BY-SA 4.0. Cargado con `tfds.load("oxford_iiit_pet")`.
