# PROYECTO INDIVIDUAL  N°2
## Data Analytics - Cryptocurrency Market
*Autor: Yuri Díaz*

¡Bienvenido!

A partir de en un dataset de 10 critptomonedas con datos de los últimos cinco años aplicaremos técnicas de analítica para obtener resultados valiosos para la toma de decisiones de una organización.



# Índice

- [Objetivos del proyecto](#objetivos-del-proyecto)
- [Selección de criptomonedas](#selección-de-criptomonedas)
- [Preparación del entorno virtual](#preparación-del-entorno-virtual)
- [Extracción de los datos](#extracción-de-los-datos)
- [Limpieza, transformación y exportación](#limpieza-transformación-y-exportación)
- [Análisis exploratorio de datos](#análisis-exploratorio-de-datos)
- [Informe de análisis](#informe-de-análisis)
- [Tecnologías usadas](#tecnologías-usadas)


# Objetivos del proyecto
Con este propósito realizaremos los siguientes procesos:
* Estudio previo para la elección de las 10 monedas a analizar.
* Extracción, Transformación y Limpieza de datos.
* EDA (Análisis exploratorio de datos).
* Informe de resultados y visualización  en un dashboard.

# Selección de criptomonedas
Parte de nuestra responsabilidad fue elegir las 10 criptomonedas para el análisis. Con este propósito realizamos un estudio previo y establecimos los siguientes criterios de selección:

* Adopción en el espacio DeFi (*Decentralized finance*).
* Alta capitalización de mercado.
* Mínimo 5 años en el ecosistema crypto. 
* Diversidad en volatilidad y riesgo.
* Vínculos con instituciones financieras centralizadas y tradicionales.

Las diez critptomonedas elegidas fueron: Bitcoin, Ethereum, Cardano, Binance Coin, Chainlink, Litecoin, Ripple, Stellar, Tether(USDT) y USDC.

# Preparación del entorno virtual
Comenzaremos creando un entorno virtual de trabajo utilizando los siguientes comandos: 

*py -m venv venv* | Otras opciones en lugar de *py* pueden ser python o python3.

Activamos el entorno con uno de estos tres comandos:

* source venv/Scripts/activate
* source venv\Scripts\activate
* source venv/bin/activate | Linux y Mac

Por último instalamos las librerías necesarias para el proyecto:

pip install -r requirements.txt.

Con el entorno listo ya podemos empezar a trabajar

# Extracción de los datos
Una vez seleccionadas las criptomonedas extrajimos los datos de la API de CoinGecko, una reconocida página que posee datos de aproximadamente 4000 monedas. Para poder conectarnos con la API usamos el módulo CoinGeckoAPI de la librería *pycoingecko*. Hicimos la petición a un *endpoint* que nos permitió extraer data histórica de los últimos cinco años de los campos precios, capitalización de mercado y volumen total.
El archivo de cada moneda se descargó en formato *.json* en la carpeta "data".


# Limpieza, transformación y exportación
* Los valores de las columnas se encontraban en forma de listas con dos valores dentro. El primero correspondía al formato de tiempo Unix y el segundo al valor de la columna. Del formato Unix extrajimos y agregamos una columna de fecha con el año, mes y día y eliminamos el formato Unix de cada valor. 

* Cambiamos los tipos de datos de las columnas modificadas.

* La página de CoinGecko también nos proporcionó una [lista completa](
https://docs.google.com/spreadsheets/d/1wTTuxXt8n9q7C4NDXqQpI3wpKu1_5bGVmP9Xz0XGSyU/edit#gid=0) con los IDs, thicker(símbolo con el que cotiza la criptomoneda) y el nombre de la moneda. De esta lista extrajimos el thicker y el id de las monedas elegidas para crear y agregar dos columnas adicionales en el DataFrame para poder identificar nuestras monedas y facilitar las operaciones posteriores.

* Revisamos valores nulos y duplicados.
* Unimos y exportamos nuestros 10 datasets en un solo archivo llamado *coins.csv* disponible en la carpeta "data".  


# Análisis exploratorio de datos
* Buscamos relaciones entre las variables.
* Usamos diferentes tipos de gráficos para encontrar tendencias, distribuciones, outliers.

<p align="center">
  <img src="https://github.com/RenatoCD/Project-2_Cryptocurrency_Analytics/blob/master/img/Captura1.jpg"  width="400"/> <img src="https://github.com/RenatoCD/Project-2_Cryptocurrency_Analytics/blob/master/img/Captura2.jpg"  width="400"/>
</p>

  
* Obtuvimos métricas como:
* Promedio de precios con diferentes rangos de fecha.
* Porcentajes de rendimiento comparados .
* Calculamos la volatilidad y la segmentamos. 
* Clasificamos según capitalización de mercado y volumen total.

# Informe de análisis
Este informe lo realizamos con base en los resultados del análisis exploratorio de datos y del dashboard hecho en PowerBi. 

KPIs
* El primer lugar de retorno lo ocupa binance coin con un promedio interanual de 249.94% y una volatilidad media de 49$.  
* Bitcoin presenta la volatilidad promedio anual más alta con 5316.72$, esto supone que es 14.2 veces mayor que la de ethereum, la cripto que le sigue con un 374.40$. 
* Chainlink es la critomoneda con volatilidad baja con un promedio de retorno más alto en 5 años: un 184.09%.

Otras métricas y resultados relevantes: 
* Quitando las dos stablecoins, el resto de criptomonedas presenta rendimientos superiores a 30% en cinco años.
* Tomando como muestra nuestras 10 criptomonedas dedujimos que el mercado se encuentra con un tendencia a la baja con una caída desde el 2021 de -44.13% hasta la realización de este informe. 
* Establecimos según su volatilidad las siguiente clasificación: 
Volatilidad baja (Valores entre 0 y 20): USDT, USDC, stellar ripple, cardano y chainlink. 
Volatilidad media(Valores entre 20 y 100): binance coin, litecoin. Volatilidad alta(Valores mayores a 100): bitcoin, ethereum.
* El máximo precio alcanzado por una criptomoneda en el periodo pertenece a bitcoin son 67.617$.
* USDC es la única criptomoneda que muestra rendimientos negativos en 5 años. Aunque estos rendimientos negativos son casi nulos: USDC: -0.10%. Le sigue otra stablecoin: USDT: 0.08%.
* Existe una relación directa entre los precios y la capitalización de mercado. Pero estas variables no son suficientes para la toma de decisiones.
* Bitcoin domina el mercado y sus movimientos influyen en las cotizaciones del resto de criptomonedas. 
* En el año 2021 se produjo el mayor volumen promedio de la historia del mercado de criptomonedas.


# Tecnologías usadas
* Librerías de Python: Pandas, Matplotlib, Seaborn, pycoingecko, json.
* PowerBI.
* Visual Studio Code, Git.  
