# Análisis de precios de perfumes en Falabella

Proyecto de web scraping y análisis de datos de la materia **Programación para Análisis de Datos** (IU Digital de Antioquia, Ingeniería de Software y Datos).

El repositorio reúne el trabajo de la Evidencia de Aprendizaje 1 (análisis del precio del perfume Khamrah en Falabella) y lo organiza como un proyecto con control de versiones en GitHub, que es lo que pide la Evidencia de Aprendizaje 2.

## Integrantes

- Santiago Sanchez Salazar
<!-- agregar aquí a los demás integrantes del grupo -->

## Qué contiene el repositorio

| Archivo | Descripción |
| --- | --- |
| `Sanchez_Santiago_Analizando_EA1.ipynb` | Notebook con el scraping, el análisis exploratorio y las gráficas. |
| `precios_perfumes_falabella.csv` | Dataset con los 5 perfumes extraídos de Falabella. |
| `requirements.txt` | Librerías de Python que necesita el notebook. |
| `.gitignore` | Archivos que no se suben al repositorio (entorno virtual, caché, etc.). |

## Página y artículo analizado

- Página: [Falabella Colombia](https://www.falabella.com.co)
- Artículo: [Perfume Khamrah Lattafa 100ml](https://www.falabella.com.co/falabella-co/product/128762286/Perfume-Khamrah-Lattafa-100ml/128762287)

## Método de scraping

Se usó **Selenium** con Chrome en modo headless para renderizar la página de cada producto y extraer el precio principal, el precio de lista, el descuento, la calificación y el número de reseñas. Como verificación, el mismo precio se extrajo también con `requests` + `BeautifulSoup` leyendo el HTML estático, y los dos métodos coincidieron en los 5 productos.

Se comparó el artículo principal contra otros 4 perfumes de la misma marca para ver cómo se forma el precio dentro del catálogo.

## Resultados

| Producto | Precio | Precio de lista | Descuento | Calificación | Reseñas |
| --- | ---: | ---: | ---: | ---: | ---: |
| Khamrah (artículo) | $119.990 | $299.000 | 59,9 % | 4,5 | 322 |
| Yara | $119.990 | $299.000 | 59,9 % | 4,7 | 924 |
| Asad | $119.990 | $290.000 | 58,6 % | 4,7 | 130 |
| Khamrah Qahwa | $174.990 | $299.000 | 41,5 % | 4,5 | 83 |
| Eclaire | $119.990 | $299.000 | 59,9 % | 3,9 | 77 |

Datos extraídos el 2026-10-26.

## Cómo ejecutar el notebook

```bash
python -m venv .venv
source .venv/Scripts/activate    # en Windows (git-bash)
pip install -r requirements.txt
jupyter notebook
```

El notebook necesita Chrome instalado, porque Selenium lo abre para leer cada página. Al correrlo de nuevo se genera el CSV con la fecha de extracción actualizada.

## Tecnologías

- Python 3.13
- Selenium + Chrome headless
- pandas
- matplotlib
- requests + BeautifulSoup (verificación y comparación)
