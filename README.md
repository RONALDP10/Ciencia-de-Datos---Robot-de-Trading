# Ciencia-de-Datos---Bot-de-Trading
Proyecto Bot de Trading para analizar el comportamiento de Bitcoin :moneybag: en tiempo real y tome decisiones de compra, venta o mantener, basándose en medias móviles simples y tendencias de mercado.

## Proceso.
Para el funcionamiento del código se establecen las siguientes etapas:

## 📥 Obtención y Tratamiento de Datos
### 📂 Importación de Datos
- Los datos históricos del precio de Bitcoin (BTC-USD) se obtienen a través de la API de yFinance.
- Los precios actuales y la tendencia de mercado se extraen de CoinMarketCap utilizando BeautifulSoup.

### 🧹 Limpieza de Datos
Se realizan las siguientes operaciones para preparar los datos:
- 📋 **Eliminación de duplicados**: Eliminamos registros con índices duplicados.
- 🧽 **Relleno de valores nulos**: Rellenamos los valores faltantes en la columna de precios con el último valor disponible.
- 📉 **Manejo de outliers**: Aplicamos el método del rango intercuartílico (IQR) para eliminar valores atípicos.

## 📊 Cálculo de Medias Móviles
Se calculan dos medias móviles:
- **SMA corto (10 periodos)**: Representa la tendencia a corto plazo.
- **SMA largo (50 periodos)**: Representa la tendencia a largo plazo.

## 🤖 Toma de Decisiones
El bot toma decisiones basadas en las siguientes reglas:
- **Comprar**: Si la SMA corta supera la SMA larga y la tendencia es alcista.
- **Vender**: Si la SMA corta está por debajo de la SMA larga y la tendencia es bajista.
- **Mantener**: Si no se cumplen las condiciones anteriores.

## 🔄 Ciclo Automatizado
El bot se ejecuta en un loop infinito, tomando decisiones cada 5 minutos, descargando nuevos datos, limpiando los datos y calculando las medias móviles para decidir la acción a tomar.

## 📊 Visualización de Resultados
Se pueden generar gráficos para visualizar el comportamiento de las medias móviles y el precio de Bitcoin utilizando bibliotecas como Matplotlib y Plotly.
