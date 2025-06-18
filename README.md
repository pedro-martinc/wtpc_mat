# ⚙️ wtpc_mat

Para el modelado de la curva de potencia de un aerogenerador se emplean **procesos gaussianos**. Se desarrollan dos estrategias para seleccionar el kernel más adecuado:

1. **MAE en validación:**  
   Entrenar un proceso gaussiano para cada kernel utilizando los datos del año 2020 como conjunto de entrenamiento, y evaluar su desempeño en validación con los datos de 2021.  
   Se selecciona el kernel con menor error absoluto medio (MAE). También pueden considerarse el coeficiente de determinación (R²) y el PICP para un análisis más preciso.

2. **Máxima verosimilitud:**  
   Entrenar un proceso gaussiano con todos los datos disponibles (2020 y 2021) y seleccionar el kernel que proporcione la mayor log-verosimilitud.

---

El notebook `gp_mae.ipynb` desarrolla la primera estrategia, mientras que `gp_likelihood.ipynb` implementa la segunda.  
Ambos están previamente ejecutados para permitir la lectura directa del procedimiento y resultados.  
Los archivos CSV con los datos se encuentran comprimidos. Para usarlos, se decomprimen sin cambiar el nombre y se colocan en la raíz.

---

## 🧪 Requisitos

Para ejecutar los notebooks, se requieren las siguientes bibliotecas de Python. Se pueden instalar individualmente con:

```bash
pip install numpy
pip install pandas
pip install matplotlib
pip install GPy
pip install scikit-learn
```

Se recomienda que la ejecución se realice desde algún IDE común como **Visual Studio Code**, con extensiones de **Jupyter** (como *Jupyter*). Basta con abrir el notebook y ejecutar todo el código pulsando `Run All`.

> ⚠️ **AVISO:** Ejecutar los experimentos para todos los kernels puede requerir aproximadamente **una hora** por notebook, dependiendo de la capacidad de cómputo del equipo empleado.
