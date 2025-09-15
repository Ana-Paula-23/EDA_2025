# EDA_2025
Avances:

*Hasta el 11/9*
- Transformación de tipo de variables de ambos dataset porque no lo levanta bien el .csv
- Filtro df_test: currency=USD, operation_type=Ventas.
- Filtros df_desarrollo: l1=Argentina, l2=regiones/provincias que corresponden, property_type = Casa, PH, Casa de campo y Departamento (opcional: considerar "otros").
- Tablas de frecuencia
- Reportes EDA de df_test original, df_test con filtros, df_desarrollo original y df_desarrollo con los filtros anteriores.
- Se quitaron las columnas ad_type y l5 de df_desarrollo porque tienen un único valor y no aportan información. FALTA QUITARLAS DE df_test.
- Filtros para ver cómo se distribuye price según currency (USD y ARS) en las bases df_ventas_sin_otros_USD y df_ventas_sin_otros_ARS.
- Creación de variales usando NLP: superficie total, superficie cubierta, cantidad de ambientes, cantidad de baños, flag más de una propiedad.
- Intento de identificar cuántas coordenadas están bien y cuántas mal (REVISAR)

- Modelo lightGBM y CV con la base sucia: 'rooms', 'bathrooms', 'bedrooms', 'surface_covered', 'surface_total', 'price'.
- Modelo lightGBM y CV con la base sucia: 'rooms', 'bathrooms', 'bedrooms', 'surface_covered', 'surface_total', 'price' + 'ambientes_npl'.

*Hasta el 14/9*
- Transformación de tipo de variables de ambos dataset porque no lo levanta bien el .csv
- Filtro df_test: currency=USD, operation_type=Ventas.
- Filtros df_desarrollo: l1=Argentina, l2=regiones/provincias que corresponden, property_type = Casa, PH, Casa de campo y Departamento (opcional: considerar "otros" **NO LO HICE**), **l3 que coincida con db_test** y **price sin NA**.
- Tablas de frecuencia
- Reportes EDA de df_test original, df_test con filtros, df_desarrollo original y df_desarrollo con los filtros_1 (los considerados hasta el 11/9) y df_desarrollo con los filtros_2 (idem anterior + filtros de l3 y price).
- Filtros para ver cómo se distribuye price según currency (USD y ARS) en las bases df_ventas_sin_otros_USD y df_ventas_sin_otros_ARS.
- Creación de variales usando NLP: superficie total (más fancy considerando el tamaño del lote), superficie cubierta, cantidad de ambientes, cantidad de baños (incluyendo toilette), flag más de una propiedad.
- Creación de variables geográficas: provincia=l2 (reemplazo Capital Federal por Ciudad Autónoma de Buenos Aires), departamento=l3 (reemplazo Capital Federal por Ciudad Autónoma de Buenos Aires) y barrios_caba (sólo con los barrios oficiales y no oficiales). Para los barrios no oficiales busqué y creé un diccionario con coordenadas aprox.
- lat y lon:
      - lat_ok y lon_ok: di vuelta las coordenadas que claramente estaban mal. NINGUNA DE TODAS LAS COORDENADAS ESTÁN EN ARG.
      - lat_inv y lon_inv: invertí las columnas lat y lon. LA GRAN MAYORÍA ESTÁN EN ARG, AUNQUE EN PROVINCIAS QUE NO ESTÁN CONSIDERADAS EN LA POBLACIÓN OBJETIVO.
      - lat_real y lon_real *(en proceso)*: Usando las columnas de provincia, departamento y barrios_caba la idea es matchear con los GEOJSON oficiales y tener coordenadas reales.
