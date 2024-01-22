# ANÁLISIS COMPLETO DE UN ACTIVO DE RENTA VARIABLE

En este notebook se desarrolló una funcionalidad que permite realizar un ANÁLISIS COMPLETO de una activo de renta variable. Se implementó una clase con varios métodos que analizan distintos aspectos relevantes. El índice de funciones se detalla a continuación (asimismo, todas las funcionalidades están documentadas)

_Para ver el demo, por favor ingresar a la Notebook "assetAnalysis.ipynb" para ver los outputs_

# INDICE DE FUNCIONES

- class AssetAnalysis:
  ÍNDICE DE FUNCIONES/MÉTODOS DE LA CLASE:
  FUNCIONES DE ANÁLISIS FUNDAMENTAL:

  1. getProfile(self):
     Esta función devuelve data básica de la compañía (datos generales) del perfil. API de Finnhub.

  2. getAFMetricsFH(self):
     Esta función devuelve todas las métricas de Análisis Fundamental de una empresa. API de Finnhub.  
     Claves: metric (métricas individuales)

  3. getAFMetricsSeriesFH(self, metrica, tipo = "annual"):
     Esta función devuelve todas la serie de la métrica de Análisis Fundamental
     seleccionada de una empresa. API de Finnhub. Devuelve los datos numéricos (dataframe) y el gráfico de evolución. El análisis
     puede ser anual ("annual") ocuatrimestral ("quarterly"). El análisis annual agrega una media móvil simple de 4 sesiones.
     El análisis quarterly agrega una media móvil simple de 10 sesiones.

  4. getCompleteProfile(self):
     Devuelve la data del perfil completo de una compañía (datos básicos). API de FMP Cloud.

  5. getBalanceSheetEvo(self, tipo, component, añoDesde, añoHasta):
     Esta función permite obtener datos y graficar la evolución de
     componentes del Balance (Estado de Situación Patrimonial) de un activo. Tanto el activo como el componente (cuenta) son parametrizables.
     La unidad de tiempo puede ser anual ("annual") o cuatrimestral. ("quarterly"). API de FMP Cloud.

  6. getResultsEvo(self, tipo, component, añoDesde, añoHasta):
     Esta función permite obtener datos y graficar la evolución de componentes
     del Estado de Resultados de un activo. Tanto el activo como el componente (cuenta) son parametrizables. La unidad de tiempo puede ser
     anual ("annual") o cuatrimestral ("quarterly"). API de FMP Cloud.

  7. getCashFlowEvo(self, tipo, component, añoDesde, añoHasta):
     Esta función permite obtener datos y graficar la evolución de componentes
     del Estado de Flujo de Efectivo de un activo. Tanto el activo como el componente (cuenta) son parametrizables. La unidad de tiempo
     puede ser anual ("annual") o cuatrimestral ("quarterly"). API de FMP Cloud.

  8. getRatioEvo(self, ratio, añoDesde, añoHasta):
     Esta función permite obtener datos y graficar la evolución anual de ratios financieros
     de un activo. Tanto el activo como el ratio son parametrizables. API de FMP Cloud.

  9. getKeyMetricsEvo(self, metrica, añoDesde, añoHasta):
     Esta función permite obtener datos y graficar la evolución anual de las métricas
     financieras clave de un activo. Tanto el activo como la métrica son parametrizables. API de FMP Cloud.

  10. getAFRating(self, añoDesde, añoHasta, ponderacion = "igual", timeframe = "semanal"):
      Esta función permite obtener datos y graficar la
      evolución del rating de un activo por sus fundamentals según la API de FMP Cloud.
      Ofrece el puntaje según 5 ratios: # - Valuación de Flujo de Fondos (DCF) # - Return on Equity (ROE) # - Return on Assets (ROA) # - Deuda sobre PN (DE) # - Precio sobre Ganancias (PER) # - Precio sobre Valor Libro (PB)
      Se puede setear año desde, año hasta y el tipo de ponderación:
      API de FMP Cloud.
      FUNCIONES DE ANÁLISIS TÉCNICO:
  11. getTechnicals(self):
      Este método permite obtener toda una serie de indicadores relevantes (MACD, RSI, ADX/DMI, EMAs, Ichimoku) para determinar la
      condición técnica del activo en particular. Esto para cada timeframe: diario, semanal y mensual. Además arroja una evaluación
      (puntaje) base 10 a modo resumen, para cada marco temporal. Ver detalle de outputs en la documentación de la función/método.

Nota: todas las funciones se encuentran adecuadamente documentadas en los lugares respectivos.

AGRADECIMIENTOS
Las funciones de Análisis Fundamental tienen aportes de código de la serie de libros "Python para Finanzas Quant" de Juan Pablo Pisano.
