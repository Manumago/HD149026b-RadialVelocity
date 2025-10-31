# Análisis de velocidad radial y tránsitos del exoplaneta HD 149026b

Este repositorio contiene el desarrollo y análisis del sistema planetario **HD 149026**, combinando datos de **velocidad radial** y **fotometría de tránsito** para caracterizar los parámetros orbitales y físicos del exoplaneta **HD 149026b**, así como la estimación de los **límites de la zona habitable** del sistema.

El trabajo combina herramientas de modelado, ajuste de curvas y métodos estadísticos en Python, validando los resultados con observaciones reportadas en la literatura.

---

## Objetivos

- Aplicar modelos de **ajuste de curvas de velocidad radial** para determinar el período orbital, la semiamplitud y la masa mínima del planeta.
- Analizar la **curva de luz de tránsito** para obtener el radio planetario y validar los parámetros orbitales.
- Calcular los **límites interno y externo de la zona habitable** utilizando los criterios de **Kasting et al. (1996)** y las actualizaciones de **Kopparapu et al. (2013)**.
- Evaluar la evolución de la zona habitable en función de la masa y luminosidad estelar.

---

##  Metodología

###  Método de velocidad radial
- Se utiliza el **efecto Doppler** para detectar variaciones periódicas en la velocidad de la estrella anfitriona.  
- A partir de los datos de velocidad radial del catálogo **NASA Exoplanet Archive**, se genera un **periodograma de Lomb–Scargle** (Astropy) para determinar el período orbital.  
- Se ajusta una función sinusoidal con `curve_fit` (SciPy) y se calcula la **masa mínima**.

### Método de tránsito
- Se emplean los datos fotométricos de **TESS** y las curvas de luz reportadas por Butler et al. (2006).  
- Se modela el tránsito con un ajuste gaussiano–simétrico.
- A partir de la profundidad del tránsito, se calcula el **radio planetario**.

###  Zona de habitabilidad
- Se aplican los modelos de **Kasting (1996)** y **Kopparapu et al. (2013)**, junto con la relación masa–luminosidad de **Duric (2004)**, para calcular los límites internos y externos de la **zona habitable (ZH)**.

- Se grafican los límites de la ZH para estrellas con masas entre **0.4 – 1 M⊙**, mostrando los criterios de *Recent Venus, Moist Greenhouse, Maximum Greenhouse* y *Early Mars*.


