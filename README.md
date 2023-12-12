# Análisis Financiero con PowerBI
# Este proyecto ha sido desarrollado por Alicia Cecilia Gómez Wallingre  

Mail:cecigomezwallingre@gmail.com  
[LinkedIn](https://www.linkedin.com/in/ceciliagomezwallingre)

### Contexto
Este proyecto tiene como finalidad realizar diferentes análisis con enfoque financiero. Se trata de un dataset que contiene diferentes tablas, que a su vez contienen diferenctes campos de información, ya organizadas con el fin de poder realizar un análisis de negocio. La información del contenido de las tablas se detalla en el apartado final. 
El análisis realizado fue el siguiente: 
* Se efectúa un Mockup como modelo del análisis a realizar
* En primer lugar se crearon todas las relaciones en la vista de Diagrama Entidad Relación.
* Posteriormente se desarrollaron los siguientes puntos:
   
#### Medidas DAX

1) Número de ventas: recuento de ventas distintas
2) Volumen vendido: cantidad total vendida
3) Ventas brutas: valor total vendido (cantidad x precio unitario)
4) Costo total: costo total de ventas (cantidad x costo unitario)
5) Precio de venta medio: valor medio de los precios unitarios
6) Descuento total: descuento total otorgado sobre las ventas
7) Descuento total auditado: el descuento total, sólo para promociones que estuvieran vigentes al momento de la venta
8) Ventas netas: ventas brutas sin descuentos
9) Ventas brutas diarias promedio: valor, en promedio, de las ventas brutas diarias. Sólo se deben contar los días en los que hubo ventas.

#### Medidas DAX de inteligencia de tiempo

1) Ventas brutas de LY: ventas brutas del año anterior
2) % Ventas Brutas LY: diferencia en porcentaje de ventas brutas entre el período actual y el mismo período del año anterior
3) Ventas brutas YTD: ventas brutas acumuladas desde el primer día del año hasta la fecha seleccionada (mes o día)
4) Ventas brutas exactas de LY: ventas brutas del mismo período del año anterior, donde los valores del año anterior se suman solo hasta la fecha más alta de los datos existentes del período actual.

#### Medidas de representación porcentual con relación al total

1) % Productos de la categoría de ventas brutas de participación: Calcula el % representativo respecto del total de la categoría (columna DcategoryProducts (categoría)). La medida debe devuelve el mismo valor para una categoría determinada, independientemente de los filtros externos aplicados a la categoría de producto.
2) % de ventas brutas genéricas a compartir: Calcula el % representativo respecto del total, independientemente de la segmentación utilizada (año, mes, categoría de producto, tiendas, etc.)
3) % de acciones de ventas brutas: Calcula el % de acciones por continente y categoría siempre totalizando el 100% en el nivel seleccionado, usa dlocalidades (continente) para agregar
dcategoryProducts (categoría) en una matriz (continente> categoría);

#### Medidas de Ranking

1) Promociones de clasificación: calcula el valor de clasificación de cada promoción, en función de las ventas netas más altas. Orden de clasificación descendente
2) % Share top 10 producto: calcula la representación de los 10 mejores productos en relación con las ventas brutas totales y segmenta el visual para cada uno de los años. Los 10 mejores productos son los 10 primeros para cada uno de los años de segmentación, es decir, esta lista de productos puede cambiar del 2021 al 2022.

#### Gestión de acceso - Row Level Segurity (RLS)

1) La primer regla será estática: Solo se mostrará el país "Estados Unidos".
2) La segunda regla será dinámica: Se crea una tabla para usar como parámetro RLS dinámico, con posibilidad de filtrar por los 3 países: "Australia", "Canadá" y "Francia". Para la creación de la tabla, se utilizaron 3 direcciones de correo electrónico ficticias:
"australia@jaarconsult.com.br", "canada@jaarconsult.com.br" y "francia@jaarconsult.com.br";
3) Se implementó RLS dinámico con solo 1 regla.

#### Conceptos de Front-End

1) En la página 'Informes' se crean botones de navegación para cambiar entre las 2 pestañas diferentes. Estos botones están en ambas pestañas.
2) Se creó un menú "Suspendido/Retráctil" colocando los filtros (visuales de segmentación) de Año, AñoMes, etc. dentro de él. Estos filtros están en ambas pestañas y sincronizados.
3) Se crea en la misma página, una medida que se pueda usar en un objeto visual de filtro (segmentador) para seleccionar entre las medidas Ventas brutas o Costo total.
4) También en esa página, se crea un gráfico para analizar la evolución de las ventas brutas vs el costo total.
5) Se muestra que promociones tuvieron el mayor retorno de ventas.
6) Se crea un selector de segmentación para un gráfico de barras horizontales, pudiendo cambiar la segmentación entre País, Tienda y Categoría de Producto.
7) En la página 'Parámetros', se realiza un análisis financieros segmentando fechas y conceptos, con análisis de texto dinámico.
8) Se realizan dos KPI's que analicen el comparativo de ventas brutas y ventas con descuento, y el aumento del 5% respecto al año anterior.

#### Contenido de tablas

##### Categoría Productos
* Categoría
* IdCategoría
  
##### Iconos Productos
* Categoría
* Icono URL

##### Localidades
* Ciudad
* Continente
* Estado
* IDLocalidad
* País
* TipoLocalidad
  
##### Tienda
* Fecha Apertura
* Fecha Cierre
* IdLocalidad
* IdTienda
* Numero de Empleados
* Razon Cierre
* Status
* Tamaño Tienda
* Tipo tienda
  
##### Productos
* Clasificación
* Color
* IdProducto
* IdSubcategoría
* Marca
* Producto
  
##### Promociones
* Código Promoción
* Fecha Inicio
* Fecha Fin
* IdPromoción
* Porcentaje de descuento
* Promoción
* Tipo Promoción
  
##### SubCategoría de Productos
* IdCategoría
* IdSubcategoría
* Subcategoría
  
##### Ventas
* Código Venta
* Costo unitario
* Fecha
* Descuento Total
* IdTienda
* IdProducto
* IdPromoción
* Precio Unitario
* Cantidad

### Conclusión
El presente análisis se centra en explorar las funciones de PowerBi con el fin de realizar análisis financieros que permitan a la empresa una toma de decisiones mas acertado. 



