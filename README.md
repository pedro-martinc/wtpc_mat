# ⚙️ wtpc_mat

Para el modelado de la curva de potencia de un aerogenerador se utilizan **procesos gaussianos** en regresión. La estrategia para seleccionar el kernel más adecuado es la siguiente:

Se entrena un modelo de regresión con procesos gaussianos con cada uno de ellos. Para este propósito, se emplea un subconjunto de los datos filtrados del 2020, y se evalúa el desempeño de cada modelo sobre otro subconjunto, también filtrado, de 2021. Se escogerá aquel kernel que presente el menor error absoluto medio (MAE). También se pueden emplear el coeficiente de determinación (R²) y el PICP (0,95) para un análisis más preciso.

---

El notebook `wtpc.ipynb` desarrolla la estrategia.
Está previamente ejecutado para permitir la lectura directa del procedimiento y resultados.  
Los archivos CSV con los datos se encuentran comprimidos. Para usarlos, se decomprimen sin cambiar el nombre y se colocan en la raíz.

---

## 🧪 Requisitos

Para ejecutar el notebook, se requieren las siguientes bibliotecas de Python. Se pueden instalar individualmente con:

```bash
pip install numpy
pip install pandas
pip install matplotlib
pip install GPy
pip install scikit-learn
```

Se recomienda que la ejecución se realice desde algún IDE común como **Visual Studio Code**, con extensiones de **Jupyter** (como *Jupyter*). Basta con abrir el notebook y ejecutar todo el código pulsando `Run All`.

> ⚠️ **AVISO:** Ejecutar los experimentos para todos los kernels puede requerir aproximadamente **media hora** por notebook, dependiendo de la capacidad de cómputo del equipo empleado.
