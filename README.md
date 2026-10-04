# Análisis de clientes de ConnectaTel

Análisis exploratorio, limpieza y segmentación de clientes de una empresa de telecomunicaciones con operaciones en México y Colombia. Proyecto del Sprint 7 del bootcamp de Análisis de Datos de TripleTen.

## 🎯 Objetivo

Entender cómo los clientes usan realmente los servicios móviles (llamadas y mensajes) para identificar patrones de uso, detectar comportamientos atípicos y definir segmentos de clientes que ayuden a optimizar la oferta de planes.

## 📂 Datasets

| Archivo | Contenido |
|---|---|
| `plans.csv` | Planes disponibles: precio, minutos, mensajes y GB incluidos, costo por excedente |
| `users_latam.csv` | 4,000 clientes: edad, ciudad, fecha de registro, plan contratado y fecha de baja |
| `usage.csv` | 40,000 registros de uso en 2024: llamadas (duración) y mensajes (longitud) |

Los datasets fueron proporcionados por TripleTen y no se incluyen en este repositorio.

## 🔄 Etapas del análisis

1. **Carga y exploración** de la estructura de los tres datasets.
2. **Calidad de datos**: nulos, sentinels (`-999` en edad, `"?"` en ciudad) y fechas imposibles (registros en 2026).
3. **Limpieza**: imputación de edad con la mediana, sentinels a nulos y verificación de nulos estructurales (MAR).
4. **Estadísticas por usuario**: total de mensajes, llamadas y minutos en 2024.
5. **Visualización y outliers**: histogramas por plan, boxplots y método IQR.
6. **Segmentación** por nivel de uso y por grupo de edad.
7. **Insight ejecutivo** con conclusiones y recomendaciones de negocio.

## 💡 Principales hallazgos

- El uso real está muy por debajo de lo que incluyen los planes: el cliente promedio envió 5.5 mensajes, hizo 4.5 llamadas y habló 23 minutos **en todo el año**.
- Los clientes Premium pagan más del doble que los Básico, pero tienen el mismo patrón de uso.
- La edad tampoco cambia el comportamiento: los tres grupos de edad tienen casi la misma distribución de niveles de uso.
- Se identificó un grupo de clientes, casi todos Premium, con un consumo de llamadas muy superior al resto (130–155 minutos al año).

## 🛠️ Herramientas

Python · pandas · numpy · matplotlib · seaborn · Jupyter Notebook

## ▶️ Cómo ejecutar el notebook

1. Abre el notebook en Google Colab:
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/stefanloosveld/connectatel-analysis/blob/main/ConnectaTel_analysis.ipynb)
2. Sube los tres archivos CSV a la sesión de Colab (ícono de carpeta → subir).
3. En la celda de carga, cambia las rutas `/datasets/...` por el nombre del archivo, por ejemplo `pd.read_csv('plans.csv')`.
4. Ejecuta todas las celdas en orden: **Entorno de ejecución → Ejecutar todas**.

## 👤 Autor

Stefan Loosveld — [GitHub](https://github.com/stefanloosveld)
