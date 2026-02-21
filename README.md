# 🥑 Avocado Sales Analysis
### Proyecto Integrador — Análisis de Ventas de Aguacate en EE.UU.

> **Grupo 8** | Análisis Exploratorio de Datos · Limpieza · Dashboard Power BI

---

## 👥 Integrantes

| N° | Nombre |
|----|--------|
| 1  | BOLLORINO MONTOYA FAVIO RENATO  |
| 2  | CABALLERO ZAMBRANO JOSÉ PATRICIO  |
| 3  | LONDO DUCHI STALYN ALFREDO  |
| 4  | MENOSCAL CHIRIGUAYA DANIEL ALEJANDRO  |
| 5  | RODAS CRUZ MIA FIORELLA  |

---

## 📋 Descripción del Proyecto

Este proyecto analiza el comportamiento de precios y volúmenes de venta de aguacate en el mercado estadounidense entre 2015 y 2018. A partir de un dataset con registros semanales por región y tipo de producto, se realizó un proceso completo de limpieza de datos, análisis exploratorio (EDA) y visualización mediante un dashboard en Power BI.

**Preguntas de negocio respondidas:**
- ¿Cómo evoluciona el precio promedio a lo largo del tiempo y qué estacionalidad se observa?
- ¿Qué relación existe entre precio promedio y volumen total (elasticidad aproximada)?
- ¿Qué regiones concentran mayor volumen y cómo varía el precio entre ellas?

---

## 📁 Estructura del Repositorio

```
avocado-sales-analysis/
│
├── data/
│   ├── dataset_avocado.csv          # Dataset original sin modificaciones
│   └── aguacates_limpio.csv         # Dataset limpio exportado tras el pipeline
│
├── notebooks/
│   └── limpieza_datos.ipynb         # Notebook completo de limpieza y EDA
│
├── dashboard/
│   └── proyecto_v3.pbix       # Archivo Power BI (conectado al dataset limpio)
│
└── README.md
```

---

## ⚠️ Aviso Importante — Configuración del Notebook

> **Este repositorio está pensado para ejecutarse de forma local.**
> El notebook `limpieza_datos.ipynb` fue desarrollado en un entorno local y **requiere un ajuste manual en la ruta de lectura del dataset** antes de ejecutarse.

### Qué modificar

Al inicio del notebook, en la celda de carga de datos, encontrarás esta línea:

```python
data = pd.read_csv("dataset_avocado.csv")
```

Debes reemplazarla por la ruta relativa correcta dentro de la estructura del repositorio:

```python
data = pd.read_csv("../data/dataset_avocado.csv")
```

### Dónde se guarda el dataset limpio

De la misma forma, la celda de exportación al final del notebook guarda el archivo en el directorio actual. Para que quede correctamente organizado dentro del repositorio, modifica la línea de exportación:

```python
# Antes
columnas_export.to_csv('aguacates_limpio.csv', index=False, encoding='utf-8')

# Después
columnas_export.to_csv('../data/aguacates_limpio.csv', index=False, encoding='utf-8')
```

Con estos dos cambios el notebook leerá el dataset original desde la carpeta `data/` y guardará el resultado limpio en esa misma carpeta, manteniendo la estructura del repositorio ordenada.

---

## 🚀 Cómo Reproducir el Análisis

### 1. Clonar el repositorio

```bash
git clone https://github.com/YaibeehBA/Grupo8-AVOCADO-SALES.git
cd avocado-sales-analysis
```

### 2. Instalar dependencias

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Ejecutar el notebook

```bash
cd notebooks
jupyter notebook limpieza_datos.ipynb
```

Ejecutar las celdas en orden secuencial. Al finalizar, el archivo `aguacates_limpio.csv` quedará guardado en la carpeta `data/`.

### 4. Explorar el dashboard

Abrir el archivo `dashboard/avocado_dashboard.pbix` con **Power BI Desktop**.

> **Nota:** Power BI Desktop es gratuito y está disponible en [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Al abrir el archivo, Power BI puede solicitar actualizar la ruta de conexión al dataset. En ese caso, apuntar al archivo `data/aguacates_limpio.csv` dentro del repositorio clonado.

---

## 🛠️ Herramientas Utilizadas

| Herramienta | Versión recomendada | Uso |
|-------------|-------------------|-----|
| Python | 3.8 o superior | Lenguaje base |
| Pandas | 1.3 o superior | Manipulación de datos |
| NumPy | 1.21 o superior | Cálculos numéricos |
| Matplotlib | 3.4 o superior | Visualización |
| Seaborn | 0.11 o superior | Visualización estadística |
| Jupyter Notebook | Cualquier versión reciente | Entorno de desarrollo |
| Power BI Desktop | Versión más reciente | Dashboard interactivo |

---

## 📊 Dataset

**Fuente:** [Avocado Prices — Kaggle]

**Descripción:** Datos semanales de ventas de aguacate en 52 regiones de Estados Unidos, entre enero 2015 y marzo 2018.

| Característica | Dataset Original | Dataset Limpio |
|----------------|-----------------|----------------|
| Filas | 18,249 | 17,576 |
| Columnas | 14 | 18 |
| Regiones | 54 | 52 |
| Retención de datos | 100% | 96.3% |

---

## 📄 Licencia

Este repositorio fue creado con fines académicos como parte del Proyecto Integrador del Grupo 8.
