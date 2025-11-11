---
title: Edvai Tp Final
emoji: 🏠
colorFrom: pink
colorTo: pink
sdk: gradio
sdk_version: 5.49.1
app_file: app.py
pinned: false
license: mit
---

# 🏠 Predictor de Precios de Propiedades en Argentina

Esta aplicación utiliza un modelo de Machine Learning para predecir el precio de propiedades en Buenos Aires y el Gran Buenos Aires (GBA) en dólares estadounidenses (USD).

## 🔗 Enlace a la aplicación

**👉 [Acceder a la aplicación en Hugging Face](https://huggingface.co/spaces/carlageier/edvai_tp_final)**

## 📸 Captura de pantalla

![image](https://cdn-uploads.huggingface.co/production/uploads/690e1efa53bc701928522cb6/bQ7UTWaT5INwY9b5nlBUZ.png)

## 🚀 Uso mediante API

Puedes consumir el modelo a través de la API usando la biblioteca `gradio_client`:

```python
# Instalar la biblioteca gradio_client
!pip install gradio_client

from gradio_client import Client

# Conectar con la aplicación desplegada en Hugging Face
client = Client("carlageier/edvai_tp_final")

# Realizar una predicción
result = client.predict(
    rooms=3,
    bedrooms=2,
    bathrooms=1,
    surface_total=60,
    surface_covered=55,
    place_name="Palermo",
    property_type="Departamento", 
    state_name="Capital Federal",
    api_name="/predict"
)

print(result)
```

**RESULTADO ESPERADO:**
```
Loaded as API: https://carlageier-edvai-tp-final.hf.space ✔
'$190,250 USD'
```

## 💡 Ejemplos adicionales

```python
# Predicción para un departamento en Belgrano
result2 = client.predict(
    rooms=4,
    bedrooms=3,
    bathrooms=2, 
    surface_total=120,
    surface_covered=110,
    place_name="Belgrano",
    property_type="Departamento",
    state_name="Capital Federal",
    api_name="/predict"
)

print(result2)

# Predicción para una casa en Lomas de Zamora
result3 = client.predict(
    rooms=3,
    bedrooms=2,
    bathrooms=2,
    surface_total=80,
    surface_covered=75, 
    place_name="Lomas de Zamora",
    property_type="Casa",
    state_name="Bs.As. G.B.A. Zona Sur",
    api_name="/predict"
)

print(result3)
```

**RESULTADOS ESPERADOS:**
```
'$285,000 USD'
'$95,000 USD'
```

## 🛠️ Características técnicas

- **Modelo:** Random Forest optimizado
- **Características utilizadas:** 
  - Ambientes, dormitorios, baños
  - Superficie total y cubierta
  - Localidad (codificada por frecuencia)
  - Tipo de propiedad (One-Hot Encoding)
  - Zona geográfica (One-Hot Encoding)
- **Framework:** Gradio para la interfaz web
- **Despliegue:** Hugging Face Spaces

## 📊 Datos

El modelo fue entrenado con datos de propiedades en venta en CABA y GBA, con información de precios en dólares USD correspondiente al período 2019-2020.

## 🎯 Funcionalidades

- Predicción de precios en tiempo real
- Interfaz intuitiva con controles deslizantes y dropdowns
- Ejemplos predefinidos para testing rápido
- API consumible programáticamente

## Comentario personal final:
No obstante se trata de un trabajo académico, a mí criterio falta como features fundamentales la antigüedad y estado de los inmuebles. 
No contábamos con este dato en el data set, quizás sí en REGEX de Descripción. 
---


