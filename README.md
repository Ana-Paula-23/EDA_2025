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
