# TP Final Analítica: Predicción y explicación del engagement y comportamiento de los jugadores en videojuegos online

## Descripción general  
Este proyecto busca **predecir y explicar el nivel de engagement** de los jugadores en videojuegos online a partir de sus características demográficas, sus hábitos de uso y las propiedades del propio juego.  
El objetivo final es **diseñar estrategias de fidelización** y **optimizar la monetización** de los usuarios dentro de plataformas de juego.


## Contexto de negocio  
Las empresas del sector de videojuegos buscan maximizar el *engagement* y la **retención de usuarios**, ya que el modelo de negocio actual se basa principalmente en **suscripciones, microtransacciones y experiencias online** más que en la venta única de títulos.  
Comprender los patrones de comportamiento de los jugadores permite desarrollar estrategias más efectivas para aumentar la interacción y el valor de vida del cliente (*LTV*).


## Dataset  
**Fuente:** [Kaggle – Predict Online Gaming Behavior Dataset](https://www.kaggle.com/datasets/rabieelkharoua/predict-online-gaming-behavior-dataset)

El dataset contiene información demográfica y de comportamiento de jugadores, incluyendo:  
- Frecuencia de sesiones semanales  
- Duración promedio de las sesiones  
- Logros desbloqueados (*AchievementsUnlocked*)  
- Nivel de *engagement* (variable objetivo)


## Hipótesis  
Se plantean las siguientes hipótesis basadas en el análisis exploratorio y la literatura sobre comportamiento de usuarios en videojuegos:
1. **H1:** Los jugadores con mayor frecuencia de sesiones presentan niveles de engagement más altos.
2. **H2:** La duración promedio de las sesiones tiene un efecto positivo sobre el engagement.
3. **H3:** La cantidad de logros desbloqueados no es un predictor significativo del engagement, dado que depende en gran parte de la mecánica del juego.
4. **H4:** Variables demográficas como el género o la ubicación geográfica podrían influir en el tipo de engagement, aunque en menor medida que los hábitos de juego.


## Objetivo  
- **Predecir** el nivel de *engagement* de los jugadores utilizando técnicas de machine learning.  
- **Explicar** cuáles son los factores que más influyen en dicho nivel.  
- **Brindar información accionable** para mejorar la retención y la monetización de los usuarios.


## Hallazgos iniciales del EDA  
Del análisis exploratorio de datos surgen diferencias claras entre los niveles de *engagement*:  

- Los jugadores con **engagement alto (High)** presentan **mayor cantidad de sesiones semanales** y **mayor duración promedio por sesión**.  
- Los niveles de **engagement bajo (Low)** muestran **menor frecuencia y tiempo de juego**, como era esperable.  
- En la variable **AchievementsUnlocked** no se observan diferencias tan marcadas entre grupos, lo que podría indicar que el número de logros desbloqueados depende más de la **mecánica del juego** que del nivel de *engagement*.  

Estas relaciones **validan el uso de las variables de comportamiento como indicadores del compromiso de los jugadores** y aportan una base sólida para la modelización predictiva posterior.


## Tests de hipótesis y validación estadística
Para validar formalmente las hipótesis planteadas, se aplicaron distintos tests estadísticos según el tipo de variable y los supuestos de normalidad y homogeneidad de varianzas:
- **ANOVA de un factor:** se utilizó para comparar medias de variables continuas (como duración promedio o sesiones semanales) entre los distintos niveles de engagement. Resultados: se observaron diferencias estadísticamente significativas (p < 0.05) en la frecuencia y duración promedio de sesiones entre grupos de engagement, confirmando H1 y H2.
- **Pruebas no paramétricas (Kruskal-Wallis):** aplicadas en los casos donde no se cumplían los supuestos de normalidad. Resultados consistentes con los del ANOVA, reforzando la validez de los hallazgos.
- **Chi-cuadrado de independencia:** empleado para evaluar la relación entre variables categóricas (como Gender, Location) y el nivel de engagement. No se encontraron asociaciones significativas (p > 0.05), lo que respalda H4 parcialmente.
- **Correlación de Pearson y VIF:** utilizadas para detectar multicolinealidad y redundancia entre variables numéricas, como PlayTimeHours, SessionsPerWeek y AvgSessionDurationMinutes.

En conjunto, los resultados confirman que los hábitos de uso son los factores más determinantes del nivel de engagement, mientras que las características demográficas juegan un rol menor o no significativo.


## Modelado Predictivo
Se entrenaron tres modelos —**Regresión Logística, Random Forest y Gradient Boosting**— para predecir el engagement de los jugadores. La Regresión Logística alcanzó un rendimiento correcto (83.7% accuracy), aunque limitado por su linealidad. Random Forest mejoró significativamente la performance (90.3%) gracias a su capacidad para capturar relaciones complejas. Finalmente, **Gradient Boosting obtuvo el mejor desempeño** (91.5%), con métricas muy equilibradas y excelente capacidad de generalización, por lo que fue elegido como **modelo final**.

En todos los modelos surgieron patrones consistentes: las variables de uso —**SessionsPerWeek, PlayIntensity y AvgSessionDurationMinutes**— fueron las más influyentes. Las variables demográficas aportaron muy poco, reforzando la conclusión de que el engagement está determinado principalmente por los hábitos de juego.


## Análisis complementario: Clustering y PCA
El clustering permitió explorar la estructura natural de los jugadores, resultando en tres grupos de tamaños equilibrados y con tendencias claras en sus niveles de engagement. Aunque no replican exactamente las etiquetas, sí reflejan **estilos de juego diferenciados**.

El PCA mostró que los dos primeros componentes explican el **72.36% de la varianza**, lo que indica que la mayor parte de la estructura del comportamiento puede resumirse en pocos ejes principales.


## Conclusiones
- Los **hábitos de juego** (frecuencia y duración de las sesiones) son los principales determinantes del engagement.
- **Gradient Boosting** es el modelo que ofrece la mejor performance predictiva y estabilidad.
- El análisis de clústeres refuerza la existencia de patrones naturales de comportamiento entre jugadores.
- Los resultados del análisis permiten derivar **insights accionables** orientando estrategias de retención y segmentación de jugadores basadas en frecuencia de juego, duración de sesiones y diseño de progresión.
