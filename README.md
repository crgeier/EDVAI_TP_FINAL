---
title: Edvai Tp Final
emoji: 🐠
colorFrom: pink
colorTo: pink
sdk: gradio
sdk_version: 5.49.1
app_file: app.py
pinned: false
license: mit
---

### Si querés ingresar a la APP: https://huggingface.co/spaces/carlageier/edvai_tp_final
### Una captura de pantalla de la aplicación en funcionamiento:
![image](https://cdn-uploads.huggingface.co/production/uploads/690e1efa53bc701928522cb6/bQ7UTWaT5INwY9b5nlBUZ.png)

### Un ejemplo de uso del endpoint que proporciona Gradio una vez desplegado:
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

### Ejemplos adicionales:

```python
# Predicción para una casa en Belgrano
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

