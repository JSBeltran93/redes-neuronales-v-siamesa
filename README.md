# Reconocimiento Facial con Redes Neuronales Siamesas

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange)
![Colab](https://img.shields.io/badge/Google%20Colab-ready-yellow)

Implementación de una **red neuronal siamesa** entrenada con **Triplet Loss** para reconocimiento facial, usando TensorFlow y Keras. Incluye preprocesamiento de imágenes faciales, generación de tripletas (ancla, positivo, negativo), evaluación por distancia de embeddings y una demostración de **one-shot learning**.

> Trabajo académico — actividad **R2-A1-S10: Redes Neuronales V**, asignatura Deep Learning - Conceptos, CADI, Universidad de Cundinamarca.

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JSBeltran93/redes-neuronales-v-siamesa/blob/main/Red_Siamesa_Reconocimiento_Facial.ipynb)

## Nota sobre el dataset

La actividad permite usar imágenes propias o de personas con consentimiento explícito. En este desarrollo se utilizó el dataset público **LFW (Labeled Faces in the Wild)**, recopilado específicamente para investigación académica en reconocimiento facial (Huang et al., 2007) y disponible directamente en `scikit-learn` (`fetch_lfw_people`). Esto evita cualquier inconveniente de consentimiento, ya que son imágenes publicadas con fines de investigación, y permite entregar la actividad dentro del plazo sin comprometer la privacidad de terceros. La misma arquitectura puede aplicarse sin cambios a un dataset de fotos propias.

## Tabla de contenido

- [Objetivo](#objetivo)
- [Contenido del repositorio](#contenido-del-repositorio)
- [Arquitectura](#arquitectura)
- [Resultados](#resultados)
- [Cómo ejecutarlo](#cómo-ejecutarlo)
- [Autor](#autor)

## Objetivo

Profundizar en el reconocimiento facial mediante redes siamesas, aplicando:

- Preprocesamiento de imágenes faciales.
- Generación de tripletas (ancla, positivo, negativo).
- Triplet Loss para el entrenamiento.
- Evaluación mediante distancia entre embeddings.
- Demostración práctica de one-shot learning.

## Contenido del repositorio

```
.
├── Red_Siamesa_Reconocimiento_Facial.ipynb   # Notebook ejecutado (Colab)
├── curva_entrenamiento.png                   # Curva de Triplet Loss
├── distribucion_distancias.png               # Distribución de distancias (positivo vs. negativo)
├── demo_one_shot.png                         # Demostración de one-shot learning
└── README.md
```

## Arquitectura

- **Red de embeddings**: CNN con 3 capas convolucionales + pooling, terminando en un vector de 64 dimensiones, normalizado con L2.
- **Red siamesa**: la misma red de embeddings se aplica a tres entradas (ancla, positivo, negativo), compartiendo pesos.
- **Triplet Loss**: minimiza la distancia (ancla, positivo) y maximiza la distancia (ancla, negativo), con un margen de separación.

## Resultados

Ver el informe PDF para los resultados numéricos completos (curva de entrenamiento, distancias promedio, precisión de verificación y demostración de one-shot learning).

## Cómo ejecutarlo

**Opción 1: Google Colab**

Abrir con el badge de arriba, o manualmente: `Archivo → Abrir notebook → GitHub`.

**Opción 2: Entorno local**
```bash
pip install tensorflow scikit-learn matplotlib numpy
jupyter notebook Red_Siamesa_Reconocimiento_Facial.ipynb
```

## Autor

**Joan Schneider Beltrán Delgado**
Especialización en Inteligencia Artificial, Universidad de Cundinamarca
