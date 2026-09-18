# RappiPlus – Análisis de Negocio y Dashboard de Rendimiento

## Descripción general

Este proyecto analiza el rendimiento comercial de **RappiPlus** mediante técnicas de análisis de datos, pruebas estadísticas y herramientas de inteligencia de negocios. El objetivo es transformar datos operativos, financieros, de marketing y comportamiento de clientes en información útil para apoyar la toma de decisiones.

El análisis incluye la revisión y limpieza de datos, rentabilidad, ventas, inversión en marketing, embudo de conversión, retención de clientes y evaluación de experimentos A/B en el proceso de compra.

## Objetivos del proyecto

* Validar y limpiar los conjuntos de datos.
* Analizar ingresos, costos, inversión en marketing y rentabilidad.
* Evaluar el rendimiento de ventas y el comportamiento de compra.
* Identificar puntos de abandono en el embudo de conversión.
* Medir la retención de clientes mediante análisis de cohortes.
* Evaluar el impacto de cambios en la interfaz de pago mediante pruebas estadísticas.
* Presentar los resultados a través de un dashboard interactivo.

## Herramientas y tecnologías

* **Python:** Carga, limpieza, validación y análisis exploratorio de datos.
* **SQL:** Análisis del comportamiento de usuarios, embudo de conversión y retención.
* **Power BI / Tableau:** Visualización de indicadores y desarrollo de dashboards.
* **Análisis estadístico:** Pruebas de hipótesis para evaluar la conversión en el proceso de pago.
* **Archivos CSV:** Datos de pedidos, catálogo de productos, inversión en marketing y experimentos.

## Fuentes de datos

El proyecto utiliza diferentes conjuntos de datos relacionados con la operación de RappiPlus:

* `rappiplus_orders_raw.csv`: Pedidos, precios, descuentos e ingresos.
* `rappiplus_catalog.csv`: Costos de productos, categorías y proveedores.
* `rappiplus_marketing_spend.csv`: Inversión en marketing por canal y país.
* `events`: Eventos e interacciones de los usuarios dentro de la plataforma.
* `users`: Información de registro de usuarios.
* `user_activity`: Actividad de los usuarios para el análisis de retención.
* `experiment_checkout_ui.csv`: Resultados del experimento A/B en el proceso de pago.

## Flujo de trabajo

### 1. Evaluación de la calidad de los datos

La primera etapa consiste en revisar y preparar los datos para el análisis.

Las principales actividades incluyen:

* Carga y exploración de los conjuntos de datos.
* Conversión de fechas al formato correcto.
* Revisión de variables numéricas y valores inválidos.
* Validación de ingresos y costos.
* Identificación y eliminación de duplicados.
* Revisión de variables categóricas.
* Exportación de los datasets limpios.

Conjuntos de datos preparados:

* `orders_clean.csv`
* `catalog_clean.csv`
* `marketing_clean.csv`

### 2. Análisis de rentabilidad

Esta etapa evalúa el desempeño financiero de RappiPlus mediante la integración de información de pedidos, catálogo e inversión en marketing.

Las principales preguntas de negocio son:

* ¿Cuál es el ingreso total?
* ¿Cuáles son los costos totales de los productos?
* ¿Cuánto se invirtió en marketing?
* ¿El negocio es rentable?
* ¿Cuál es la utilidad total?
* ¿Cuál es el valor promedio de pedido?
* ¿Cuál es el promedio de productos por pedido?
* ¿Qué productos tienen mayor volumen de ventas?
* ¿Qué canales de marketing reciben mayor inversión?

### 3. Análisis del embudo de conversión

Se utiliza SQL para analizar el comportamiento de los usuarios durante el proceso de compra.

El análisis permite:

* Contabilizar usuarios únicos por evento.
* Organizar los eventos según el recorrido del cliente.
* Calcular las tasas de conversión entre etapas.
* Identificar el mayor punto de abandono.
* Calcular la conversión final a compra.

Este análisis ayuda a detectar oportunidades para mejorar la experiencia del usuario e incrementar la cantidad de compras completadas.

### 4. Análisis de retención de clientes

La retención se analiza mediante cohortes utilizando las tablas `users` y `user_activity`.

El proceso incluye:

1. Asignar a los usuarios una cohorte según su mes de registro.
2. Medir la actividad semanal después del registro.
3. Calcular los usuarios retenidos durante las semanas 1, 2 y 3.
4. Calcular el porcentaje de retención para cada cohorte.

Las métricas utilizadas incluyen:

* `retenido_w1`
* `retenido_w2`
* `retenido_w3`
* `semana_1`
* `semana_2`
* `semana_3`

El objetivo es comprender con qué frecuencia los usuarios regresan a la plataforma después de registrarse.

### 5. Prueba A/B del proceso de pago

El proyecto evalúa si un cambio en la interfaz del proceso de pago afecta la conversión de compra.

La métrica principal es:

* `conversion = 1`: el usuario completa una compra.
* `conversion = 0`: el usuario no completa una compra.

El análisis estadístico incluye:

* Definición de la hipótesis nula y alternativa.
* Selección de una prueba estadística adecuada.
* Establecimiento del nivel de significancia.
* Interpretación de los resultados.
* Evaluación de si el cambio en la interfaz tiene un impacto estadísticamente significativo en la conversión.

### 6. Dashboard de inteligencia de negocios

Los datasets limpios se utilizan para desarrollar un dashboard interactivo en Power BI o Tableau.

#### Dashboard ejecutivo

El dashboard ejecutivo presenta los principales indicadores de rendimiento:

* Ingresos totales.
* Utilidad total.
* Inversión total en marketing.
* Valor promedio de pedido.
* Promedio de productos por pedido.
* Tendencias mensuales de ingresos y utilidad.
* Ingresos y utilidad por producto o categoría.
* Rendimiento acumulado del periodo.

#### Dashboard de detalle y análisis

El dashboard detallado permite explorar el desempeño a nivel de producto y pedido.

Sus principales elementos incluyen:

* Tabla detallada de pedidos.
* Métricas de producto, cantidad, ingresos, costos y utilidad.
* Formato condicional para identificar utilidades positivas y negativas.
* Volumen de ventas por producto.
* Análisis detallado por producto.
* Filtros por fecha, categoría, producto y otras dimensiones de negocio.

## Preguntas principales de negocio

El proyecto busca responder las siguientes preguntas:

* ¿RappiPlus genera utilidades?
* ¿Qué productos y categorías contribuyen más a los ingresos?
* ¿Qué canales reciben mayor inversión en marketing?
* ¿En qué etapa abandonan los usuarios el proceso de compra?
* ¿Cuál es la tasa final de conversión?
* ¿Qué tan efectivamente se retienen los nuevos usuarios?
* ¿El cambio en la interfaz de pago mejora la conversión?
* ¿Qué áreas del negocio representan oportunidades de mejora?

## Valor para el negocio

El proyecto combina preparación de datos, análisis financiero, SQL, pruebas estadísticas y desarrollo de dashboards para apoyar la toma de decisiones.

Los resultados pueden ayudar a:

* Monitorear ingresos y rentabilidad.
* Identificar costos o inversiones de marketing poco eficientes.
* Mejorar la conversión durante el recorrido del cliente.
* Comprender los patrones de retención.
* Evaluar cambios en productos y experiencia de usuario.
* Priorizar oportunidades de negocio basadas en datos.

## Entregables

* Datasets limpios en formato CSV.
* Notebook de Python con la preparación y análisis de datos.
* Consultas SQL para el embudo de conversión y retención.
* Análisis estadístico del experimento de pago.
* Dashboard interactivo en Power BI o Tableau.
* Insights de negocio y recomendaciones accionables.

## Estructura del proyecto

```text
RappiPlus-Analisis-de-Negocio/
│
├── data/
│   ├── orders_clean.csv
│   ├── catalog_clean.csv
│   ├── marketing_clean.csv
│   ├── rappiplus_catalog.csv
│   └── rappiplus_marketing_spend.csv
│
├── notebooks/
│   └── S12 Estudiante_Proyecto_Final.ipynb
│
├── dashboard/
│   └── RappiPlus_Dashboard.pbix
│
└── README.md
```

## Conclusión

Este proyecto demuestra cómo combinar Python, SQL, análisis estadístico e inteligencia de negocios para evaluar el rendimiento comercial y generar insights accionables. El análisis ofrece una visión integral de la rentabilidad, el comportamiento de los clientes, la inversión en marketing, la conversión y la retención de usuarios de RappiPlus.

