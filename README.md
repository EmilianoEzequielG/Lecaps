# LECAPS 

Lecaps es una libreria que tiene como finalidad calcular a tiempo real las tasas implicitas que otorgan las Letras Capitalizables del Tesoro de la Republica Argentina 🇦🇷 

## Versiones: 

- `1.0.0`: Letras Capitalizables al 13/07/2024. 

## Instalacion: 

``` python 
pip install Lecaps
import lecaps

```

## Usos

### Lista de Letras

Dentro de la libreria se incluye un lista con las `lecaps` vigentes a la fecha. La misma se invoca con `lista_lecaps`


``` python 
lecaps_vigentes = lista_lecaps
print(lecaps_vigentes)

```

### Funciones.

Dentro de la libreria especificada cada `lecap` es una clase. De esta manera, cada una de ellas posee los siguientes atributos: 

- `vencimiento`: Fecha de vencimiento. *(Incluye diferencias en dias)*
- `amortizacion`: Precio Final. 

``` python 
# Tomamos como ejemplo la S14O4

S14O4 = S14O4
print(S14O4.vencimiento)
print(S14O4.amortizacion)

```

### Funciones


Asimismo, cada `Lecap` posee dos metodos `info` y `Tasas`.

Dentro del método `info`, se incluye un resumen del `vencimiento` y `amortizacion` de la `lecap`. 

``` python 
# Tomamos como ejemplo la S14O4

S14O4_info = S14O4.info()
print(S14O4_info)

```
Dentro del método `Tasa` se calculan las variables a saber: 

- `TNA`: Tasa Nominal Anual. 
- `TEA`: Tasa Efectiva Anual.
- `TEM`: Tasa Efectiva Mensual.
- `REN`: Rendimiento a vencimiento. 
- `DUR`: Cantidad de meses a fecha de vencimiento. Base de 360 dias.

Para dicho cálculo se deberá ingresar el precio como párametro. El output es un Diccionario.

``` python 
# Tomamos como ejemplo la S14O4

S14O4_tasas = S14O4.Tasas(110.3)
print(S14O4.tasas)

```

### Funciones: 

Se incluyen: 

- `lecaps.days360(end_date = YYYY-MM-DD, today = None)`: Calcula la diferencia de dias en base 360. Si `today`es `None`toma la fecha que arroja la funcion `get_start_date()`

- `lecaps.lecaps_vigentes(lecaps_nombres = lista_lecaps)`: Arroja tickets de lecaps vigentes. 

- `lecaps.imprimir_tasa_lecaps(lecaps_nombres = lista_lecaps, precios = None)`: Arroja la `TNA`, `TEM` o `TEA`. Se debe incluir un vector de Precios. 

- `lecaps.curva_de_tasas(lecaps_list = lista_lecaps, precios = None)`: Arroja la curva de tasas. Se debe incluir un vector de precios. 

``` python 
precios = [107.60, 105.670, 107.400, 105.280, 102.750, 117.10, 112.950, 103.71, 101.100, 131.150, 115.500, 108.7]

# Lista
lecaps_vigentes()

# Tasas
imprimir_tasa_lecaps(precios)

# Curva
curva_de_tasas(precios)
```

