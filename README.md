
# Continuación de: Introducción a R y análisis exploratorio de datos (AED o EDA)

Estudia este texto, y responde a los siguientes mandatos. Donde veas
`...` debes colocar lo que corresponda para cumplir el mandato. **Teje
tu documento sólo cuando hayas completado todos los mandatos y no te
queden `...`**. Ejecuta tu código en la consola de R, línea a línea.
Recuerda configurar `Chunck Output in Console`.

## Paquetes y conjuntos de datos

Consulta las referencias sobre los paquetes necesarios y los conjuntos
de datos
[`doubs`](https://github.com/biogeografia-201902/material-de-apoyo/blob/master/ref/introduccion-a-r.md#el-conjunto-de-datos-doubs),
[`BCI`](https://github.com/biogeografia-201902/material-de-apoyo/blob/master/ref/introduccion-a-r.md#el-conjunto-de-datos-bci)
y
[`mite`](https://github.com/biogeografia-201902/material-de-apoyo/blob/master/ref/introduccion-a-r.md#el-conjunto-de-datos-mite).
Recuerda que `doubs` es un conjunto de datos incluido en una lista,
mientras que `BCI` y `mite` tienen las matrices de comunidad y ambiental
por separado.

``` r
library(...)
library(...)
data(...)
data(...)
data(...)
data(...)
data(...)
```

## Basicos de una matriz de comunidad

Consulta [esta
referencia](https://github.com/biogeografia-201902/material-de-apoyo/blob/master/ref/introduccion-a-r.md#b%C3%A1sicos-de-una-matriz-de-comunidad)
y cambia los `...` en los bloques de código a continuación por lo que
corresponda.

  - Número de sitios de cada conjunto (doubs, BCI, mite)

<!-- end list -->

``` r
nrow(...)
nrow(...)
nrow(...)
```

  - Riqueza numérica de especies por sitio de `BCI`

<!-- end list -->

``` r
specnumber(...)
```

  - Riqueza numérica por sitios de `mite`. Adicionalmente, mostrar los
    sitios en orden ascendente y descendente según dicha variable

<!-- end list -->

``` r
sort(specnumber(...))
sort(specnumber(...), ...) #Usa la ayuda para determinar qué argumento debes colocar aquí
```

  - Abundancia (número de individuos) de cada especie del conjunto
    `doubs`

<!-- end list -->

``` r
colSums(...)
```

  - Abundancia por sitios (especies combinadas, *species pooled*) del
    conjunto `doubs`

<!-- end list -->

``` r
rowSums(...)
```

  - Riqueza numérica en `doubs` (no por sitios)

<!-- end list -->

``` r
specnumber(colSums(...))
```

  - Abundancia total en `doubs` (no por especie ni por sitios)

<!-- end list -->

``` r
sum(colSums(...))
```

  - De los conjuntos BCI y `mite`, ¿Cuál tiene más riqueza? Interpreta
    por qué entiendes que hay tanta diferencia de riqueza entre ambos
    conjuntos.
    
      - Tu respuesta aquí: …

<!-- end list -->

``` r
specnumber(colSums(...))
specnumber(colSums(...))
```

## Diagramas de dispersión y correlación

Consulta [esta
referencia](https://github.com/biogeografia-201902/material-de-apoyo/blob/master/ref/introduccion-a-r.md#diagrama-de-dispersi%C3%B3n)
y cambia los `...` en los bloques de código a continuación por lo que
corresponda.

  - Inspección gráfica de la correlación (habría que verificar algunos
    supuestos, pero nos tomamos una licencia temporal). Realiza un
    diagrama de dispersión de las variables fosfatos y demanda biológica
    de oxígeno. ¿Existe relación entre ambas variables? ¿Directa o
    inversa? ¿Es lineal? Interpreta el resultado.
    
      - Tu respuesta aquí: …

<!-- end list -->

``` r
library(...)
ggplot(data = ...) +
  geom_point(mapping = aes(x = ..., y = ...))
```

  - El siguiente bloque de código muestra el valor de coeficiente de
    correlación lineal entre las variables anteriores. Interpreta el
    resultado.
    
      - Tu respuesta aquí: …

<!-- end list -->

``` r
cor(doubs$env$bdo, doubs$env$pho)
cor.test(doubs$env$bdo, doubs$env$pho)
```

  - Realiza histogramas de ambas variables, uno por cada una. ¿Hacia
    dónde presentan sesgos ambas variables (derecha o izquierda)? ¿Por
    qué? ¿Es oportuno medir la correlación lineal entre estas variables?
    
      - Tu respuesta aquí: …

<!-- end list -->

``` r
ggplot(data = ...) +
  geom_histogram(mapping = aes(x = ...), bins = 10)
ggplot(data = ...) +
  geom_histogram(mapping = aes(x = ...), bins = 10)
```

  - Diagrama de cajas, *boxplot*. Realiza un diagrama de caja del
    contenido de agua del substrato (`WatrCont`) y la densidad de
    arbustos (`Shrub`). Interpreta el resultado.
    
      - Tu respuesta aquí: …

<!-- end list -->

``` r
ggplot(data = ...) +
  geom_boxplot(mapping = aes(x = ..., y = ...))
```
