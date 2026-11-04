# Riesgo de desnutrición crónica infantil en el Perú

Código del estudio con la Encuesta Demográfica y de Salud Familiar (ENDES) 2007–2025: preparación de datos, entrenamiento y evaluación del modelo LightGBM, y aplicación web en Streamlit.

La herramienta sirve para priorizar a niños para su evaluación, no para diagnosticar.

## Ejecutar la aplicación

Requiere Python 3.12. El modelo entrenado ya está en `models/`.

```bash
pip install -r app/requirements.txt
python -m streamlit run app/main.py
```

## Reproducir el estudio

Los datos no se incluyen. Este comando los descarga del portal de microdatos del INEI:

```bash
make ingest
```

Los scripts de `scripts/` siguen el orden de las fases de CRISP-DM:

| Carpeta | Fase |
| --- | --- |
| `scripts/01_data_understanding/` | Comprensión de los datos |
| `scripts/02_data_preparation/` | Preparación de los datos |
| `scripts/03_modeling/` | Modelado y evaluación |

## Estructura

| Carpeta | Contenido |
| --- | --- |
| `mnp/` | Paquete con la descarga, limpieza, integración y evaluación |
| `app/` | Aplicación web |
| `models/` | Modelo entrenado y sus metadatos |
| `tests/` | Pruebas |

## Umbrales

El artículo compara los modelos con el umbral de 0.5. La aplicación usa 0.45 para detectar más casos.

## Autores

Abel Is-Boset Guevara Huasco, Zulin Pamela Vallejos Cotrina y Verónica Lisseth Vergara Rojas. Universidad Peruana Unión.
