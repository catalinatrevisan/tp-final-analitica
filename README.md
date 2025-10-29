# TP Final Analítica
# Predicción y explicación del engagement y comportamiento de los jugadores en videojuegos online

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
Los hábitos de uso de los jugadores —como la **frecuencia de las sesiones**, la **duración promedio** y los **logros desbloqueados**— son los factores que más influyen en el nivel de *engagement* en videojuegos online.


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
