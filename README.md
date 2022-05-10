# AED - Ejercicios primer parcial

## Ficha 1: Fundamentos

### **1. División con resto**

Plantear un script (directamente en el shell de Python) que permita informar, para dos valores *a* y *b*
 el resultado de la división a/b y el resto de esa división.

```python
Abra el shell de Python, y simplemente transcriba una por una
las siguientes instrucciones (recuerde que el signo >>> es el
prompt o cursor del shell y no debe escribirlo):

>>> a = 12
>>> b = 3
>>> print('a/b =', a/b, 'y el resto es:', a%b)
```

### **2. Cuadrado de un binomio**

Un binomio al  cuadrado (suma) es igual al cuadrado del primer término, más el doble producto del primero por el segundo más el cuadrado del segundo.

Plantear un script directamente en el shell de Python, que permita mostrar, para dos valores *a* y *b*, el valor del cuadrado del binomio.

```python
#Abra el shell de Python, y simplemente transcriba una por una 
#las siguientes instrucciones (recuerde que el signo >>> es el 
#prompt o cursor del shell y no debe escribirlo):

>>> a = 3
>>> b = 5
>>> t1 = (a + b) * (a + b)
>>> t2 = a*a + 2*a*b + b*b
>>> print(t1, 'es igual a', t2)
```

### **3. Área de un triángulo**

Desarrolle un programa para calcular el área de un triángulo, cargando por teclado el valor de la base, pero sabiendo que su altura es igual al cuadrado de la base. (Observar que la altura no es un dato... sólo se indica la forma de calcularla de acuerdo a la base que *sí* es un dato).

```python
# Titulos y lectura de datos
print('Calculo del area de un triangulo')
base = float(input('Ingrese la base del triangulo: '))

# Procesos
# Se obtiene la altura del triangulo
h = base ** 2
area = (base * h)/2

# Presentacion de resultados
print('El area del triangulo es:', area)
```

### **4. Últimos dígitos**

¿Cómo usaría el operador resto (%) para obtener el valor del último dígito de un número entero? ¿Y cómo obtendría los dos últimos dígitos? Desarrolle un programa que cargue un número entero por teclado, y muestre el último dígito del mismo (por un lado) y los dos últimos dígitos (por otro lado) [Ayuda: ¿cuáles son los posibles restos que se obtienen de dividir un número cualquiera por 10?]

```python
# Titulo y carga de datos
print('Obtener los ultimos digitos de un numero')
numero = int(input('Ingrese un numero: '))

# Procesos
unidad = numero % 10
decenas = numero % 100

# Presentacion de resultados
print('El ultimo digito del numero', numero, 'es', unidad)
print('Los ultimos 2 digitos del numero', numero, 'son', decenas)
```

### **5. Conversión de medidas**

Desarrolle un programa para convertir una medida dada en *pies* a sus equivalentes en:

- yardas
- pulgadas
- centímetros
- metros

Sabiendo que: 1 pie = 12 pulgadas, 1 yarda = 3 pies,  1 pulgada = 2.54 centímetros, 1 metro = 100 centímetros.

```python
# Titulo y carga de datos
print('Conversion de distancias')
pies = float(input('Ingrese la distancia en pies que desea convertir: '))

# Procesos
yardas = pies / 3
pulgadas = pies * 12
centimetros = pulgadas * 2.54
metros = centimetros / 100

# Presentacion de resultados
print('En', pies, 'pies hay', yardas, 'yardas')
print('En', pies, 'pies hay', pulgadas, 'pulgadas')
print('En', pies, 'pies hay', centimetros, 'centimetros')
print('En', pies, 'pies hay', metros, 'metros')
```

### **6. Viaje Córdoba-Rosario**

Un vehículo parte de la ciudad de Córdoba y se dirige a Rosario por autopista. La distancia aproximada entre ambas ciudades es de 400 kilómetros. El vehículo se desplaza con velocidad promedio de 122 km/h. Desarrolle un programa que calcule el tiempo total en horas que demorará ese vehículo en llegar a Rosario. De nuevo, no es necesario convertir a horas, minutos y segundos: exprese en resultado como un número real, tal cual lo haya obtenido del cálculo.

```python
# Datos: una constante...
VELOCIDAD_PROMEDIO = 122

# Titulos
print('Calculo de tiempo de llegada en un viaje')

# Procesos
# Regla de tres: si en promedio son 122 km en una hora, 400 km se recorren en...
horas = 400 / VELOCIDAD_PROMEDIO

# Presentacion de resultados
print('La cantidad de horas que tarda de Cordoba a Rosario es de', horas)
```

### **7. Precio del boleto**

Se desea conocer el precio de un boleto de viaje en ómnibus de media distancia. Para el cálculo del mismo se debe considerar el monto base (que se cobra siempre), más un valor extra calculado en base a la cantidad de kilómetros a recorrer:  Por cada kilómetro a recorrer se cobra $0.30 de adicional.

```python
# Constantes
ADICIONAL_KM = 0.30

# Titulo y carga de datos
print('Costo del boleto de un viaje')
costo_base = float(input('Ingrese el costo base del boleto: '))
kilometros = int(input('Ingrese los kilometros a recorrer: '))

# Procesos
adicional = kilometros * ADICIONAL_KM
costo_total = costo_base + adicional

# Presentacion de resultados
print('El costo del viaje es', costo_total)
```

## Ficha 02: Estructuras Secuenciales

### **1. Cuadrados y cubos**

Leer dos números y calcular:

- La suma de sus cuadrados.
- El promedio de sus cubos.

```python
# Titulo y carga de datos
print('Suma de cuadrados y promedio de cubos')
n1 = int(input('Ingrese el primer numero: '))
n2 = int(input('Ingrese el segundo numero: '))

# Procesos
# Calculo de los cuadrados...
cuad1 = n1 ** 2
cuad2 = n2 ** 2

# Calculo de los cubos...
cubo1 = n1 ** 3
cubo2 = n2 ** 3

# Calculo de la suma y el promedio...
suma = cuad1 + cuad2
prom = (cubo1 + cubo2) / 2

# Visualización de resultados
print('Suma de los cuadrados:', suma)
print('Promedio de los cubos:', prom)
```

### **2. Descuento en medicinas**

Calcular el descuento y el monto a pagar por un medicamento cualquiera en una farmacia (cargar por teclado el precio de ese medicamento) sabiendo que todos los medicamentos tienen un descuento del 35%. Mostrar el precio actual, el monto del descuento y el monto final a pagar.

```python
# Titulo y carga de datos
print('Calculo de descuento en un medicamento')
precio_actual = float(input('Ingrese el precio actual: '))

# Procesos
# Calculo del descuento...
descuento = precio_actual * 0.35

# Calculo del nuevo precio...
precio_nuevo = precio_actual - descuento

# Visualización de resultados
print('Precio original:', precio_actual)
print('Descuento del 35%:', descuento)
print('Nuevo precio:', precio_nuevo)
```

### **3. Ecuación de Einstein**

La famosa ecuación de *Einstein* para conversión de una masa *m* en energía viene dada por la fórmula:

E = mc2

Donde *c* es la velocidad de la luz cuyo valor es *c = 299792.458 km/seg.* Desarrolle **un programa que lea el valor una masa *m* en kilogramos y obtenga la cantidad de energía *E* producida en la conversión.

```python
# Constantes
C = 299792.458

# Titulo y carga de datos
print('Calculo de conversion de masa en energia (Einstein)')
masa = float(input('Ingrese la masa del objeto que desea calcular: '))

# Procesos
e = masa * (C ** 2)

# Visualización de resultados
print('La energia de la masa ingresada es:', e)
```

### **4. Polinomio de segundo grado**

Desarrollar un programa que cargue por teclado los coeficientes *a*, *b* y *c* de un polinomio de segundo grado, y calcule y muestre el valor del polinomio en el punto *x* (cargando también *x* por teclado). Además, para el mismo polinomio, calcule y muestre el valor del *discriminante* de la fórmula para el cálculo de las raíces de la ecuación.

```python
# Titulo y carga de datos
print('Calculo de polinomio y discriminante ecuacion 2do. grado')
a = float(input('Ingrese el valor de la constante a del polinomio: '))
b = float(input('Ingrese el valor de la constante b del polinomio: '))
c = float(input('Ingrese el valor de la constante c del polinomio: '))
x = float(input('Ingrese el valor de la x del polinomio: '))

# Procesos
y = a * (x ** 2) + b * x + c
discriminante = b ** 2 - 4 * a * c

# Presentacion de resultados
print('El valor del polinomio en el valor x=', x, 'es:', y)
print('El discriminante del polinomio es:', discriminante)
```

### **5. Cálculo de ángulos**

Se sabe que la suma de dos ángulos desconocidos (*alfa* + *beta* ) es igual a cierto valor *x*  que se carga por teclado. Además se sabe que la diferencia entre esos mismos dos ángulos (*alfa*  - *beta*) es igual a otro valor *y* que también se carga por teclado. Desarrolle un programa que dados los valores *x* e *y*, determine el valor de los dos ángulos *alfa* y *beta* . No es necesario convertir a grados, minutos y segundos el valor de cada ángulo: expréselos como números reales, tal cual hayan sido obtenidos.

```python
# Titulos y carga de Datos
print('Calculo de angulos')
x = float(input('Ingrese el valor de la suma de los angulos a buscar: '))
y = float(input('Ingrese el valor de la resta de los angulos a buscar: '))

# Procesos: se sabe que:
# x = alfa + beta
# y = alfa - beta

# De donde:
# x = alfa + beta
# =>  alfa = x - beta

# Por lo tanto:
# y = alfa - beta
# => y = x - beta - beta
# => y = x - 2*beta
# => y + 2*beta = x
# => 2*beta = x - y
# => beta = (x-y)/2

# Entonces:
# Si y = alfa - beta
# => alfa = y + beta

beta = (x-y)/2
alfa = y + beta

print('Valor del angulo alfa:', alfa)
print('Valor del angulo beta:', beta)
```

### **6. Precio de venta**

Conociendo el precio de lista de un artículo, determinar:

- Precio de venta al contado (10% de descuento)
- Precio de venta con tarjeta (5% de recargo)

```python
# Titulo y carga de datos
print('Precios de venta')
lista = (int(input('Ingrese precio de lista del artículo: ')))

# Procesos
contado = lista - lista * 10/100
tarjeta = lista + lista * 5/100

# Presentacion de resultados
print ("Precio contado $:", contado)
print ("Precio con tarjeta $:", tarjeta)
```

### **7. Votación en el Congreso**

En el Congreso se vota la sanción de una ley muy importante. Desarrollar un programa que permita ingresar la cantidad de votos a favor y en contra, e informe el porcentaje obtenido en cada caso.

```python
# Titulo y carga de datos
print('Porcentajes de votos parlamentarios')
votos_favor_ley = int(input('Ingrese cantidad de votos a favor de la ley: '))
votos_encontra_ley = int(input('Ingrese cantidad de votos en contra: '))

# Procesos
total = votos_favor_ley + votos_encontra_ley
porcentaje_favor = votos_favor_ley / total * 100
porcentaje_contra = votos_encontra_ley / total * 100

# Presentacion de resultados
print('El porcentaje de votos a favor fue de', porcentaje_favor, '%')
print('El porcentaje de votos en contra fue de', porcentaje_contra, '%')
```

### **8. Rinde de un Campo Agricola**

Un productor agrícola desea saber cuantos quintales de trigo puede producir en su parcela. Se pide ingresar el largo y el ancho en metros de la parcela y determinar el rinde sabiendo que en 10 m2 se obtienen 2 quintales.

```python
largo = int(input('Ingrese el largo de la parcela: '))
ancho = int(input('Ingrese el ancho de la parcela: '))

superficie = largo * ancho
rinde = (superficie * 2) // 10

print('El rinde que obtiene el productor en', superficie, 'metros cuadrados')
print('es de', rinde, 'quintales')
```

### **9. Datos de un rectángulo**

Hacer un programa que tome como entrada el ancho y el alto de un rectángulo y determine el perímetro y la superficie del mismo.

```python
# Carga de datos
ancho = int(input('Ingrese el ancho del rectángulo: '))
alto = int(input('Ingrese el alto del rectángulo: '))

# Cálculos
perimetro = alto * 2 + ancho * 2
superficie = alto * ancho

# Salidas
print('El perímetro del rectángulo ingresado es:', perimetro)
print('La superficie es:', superficie)
```

## Ficha 03: Tipos Estructurados Básicos

## **1. Plazo fijo**

Desarrollar un programa que cargue por teclado la cantidad de dinero depositada en plazo fijo por un cliente de un banco y calcular el saldo que tendrá esa cuenta al vencer el plazo fijo, sabiendo que el interés pactado era de 2.3% y que el banco cobra una tasa fija de gastos por servicios financieros igual $20 por cuenta.

```python
# Titulo y carga de datos
print('Calculo de interés y saldo final en un plazo fijo')
capital = float(input('Ingrese el capital del plazo fijo: '))

# Procesos
capital_final = capital * 1.023 - 20

# La función round(x, n) retorna el número flotante x,
# pero redondeado a n digitos a la derecha del punto decimal.
capital_final = round(capital_final, 2)

# Presentacion de resultados
print('El capital final que se obtiene del plazo fijo es:', capital_final)
```

## **2. Fecha como cadena**

Desarrollar un programa que cargue por teclado una cadena de caracteres que se supone representa una fecha en formato 'dd/mm/aaaa', y muestre por separado el día, el mes y el año. Ejemplo: si la cadena ingresada es '16/03/2016' el programa debe mostrar: 'Día: 16  -  Mes: 03  -  Año: 2016'.

```python
# Titulo y carga de datos
print('Ver una fecha en diferente formato')
fecha = input('Cargue la fecha en formato dd/mm/yyyy (incluyendo ceros): ')

# Procesos
dia = fecha[0] + fecha [1]
mes = fecha[3] + fecha[4]
anio = fecha[6] + fecha[7] + fecha[8] + fecha[9]

# Presentacion de Resultados
print('Dia:', dia, '- Mes:', mes, '- Año:', anio)
```

### **3. Importe como cadena**

Desarrollar un programa que cargue por teclado un importe (cantidad de dinero) expresado como número en coma flotante y muestre un mensaje con esa cantidad pero en dos formatos: en uno debe aparecer precedida por el signo '$' y en el otro debe aparecer precedida por la palabra "pesos".

```python
# Titulo y carga de datos
print('Visualización de un importe en forma de cadena')
importe = float(input('Ingrese un importe: '))

# Procesos
r1 = '$' + str(importe)
r2 = 'pesos ' + str(importe)

# Presentacion de resultados
print('Importe en formato 1:', r1)
print('Importe en formato 2:', r2)
```

### **4. Duración de un vuelo**

Desarrollar un programa que, conociendo el horario de partida y llegada de un vuelo (hora y minutos), determine cuál es su duración en minutos. Si el viajero necesita luego 45 minutos más para ir del aeropuerto al hotel que ha reservado, ¿a qué hora llegara al mismo?

```python
TIEMPO_TAXI = 45

# Titulo y carga de datos
print('Determinacion de tiempo de llegada a aeropuerto')
print('Las horas se ingresaran en formato hh:mm (ejemplo: 14:45 o 05:30)')
partida = input('Ingrese la hora de partida en formato hh:mm :')
llegada = input('Ingrese la hora de llegada en formato hh:mm :')

# Procesos

# Sacamos la hora de partida y la convertimos a número entero...
hp = partida[0] + partida[1]
hora_partida = int(hp)

# Ahora los minutos de esa hora, en formato entero...
mp = partida[3] + partida[4]
minutos_partida = int(mp)

# Sacamos la hora llegada y hacemos lo mismo...
hl = llegada[0] + llegada[1]
hora_llegada = int(hl)

# Igual se procede con los minutos...
ml = llegada[3] + llegada[4]
minutos_llegada = int(ml)

# Transformamos hh de la hora de partida a minutos
# y la acumulamos a los mm de los minutos de partida
minutos_partida = minutos_partida + hora_partida * 60

# Transformamos la hh de la hora de llegada a minutos
# y la acumulamos a los mm de los minutos de llegada
minutos_llegada = minutos_llegada + hora_llegada * 60

# Duracion del viaje...
duracion_viaje_minutos = minutos_llegada - minutos_partida
hora_llegada_hotel = (minutos_llegada + TIEMPO_TAXI) // 60
minutos_llegada_hotel = (minutos_llegada + TIEMPO_TAXI) % 60

# Presentacion de resultados
print('La duracion del viaje es de:', duracion_viaje_minutos, 'minutos')
print('Llega a las', (str(hora_llegada_hotel) + ':' + str(minutos_llegada_hotel)))
```

### **5. Control electoral**

Desarrollar un programa de control electoral en un centro vecinal, en el que se ingresen, para cierto candidato: apellido, nombre y cantidad de votos. Luego presentar en pantalla un resumen que muestre: iniciales del candidato, cantidad de votos entre paréntesis, y debajo una línea con tantas  "x" como votos obtenidos (por ejemplo, el candidato obtuvo 4 votos, deberá aparecer una línea como esta:  "xxxx"  con cuatro letras "x") (Asumimos que en el centro vecinal no hay demasiados electores, de forma que podamos estar seguros que no habrá miles o millones de votos... sólo unos pocos para darle sentido al enunciado).

```python
print('Resumen eleccion centro vecinal')
apellido = input('Ingrese el apellido del candidato: ')
nombre = input('Ingrese el nombre del candidato: ')
votos = int(input('Ingrese la cantidad de votos que obtuvo: '))

# Procesos
iniciales = nombre[0] + apellido[0]
cantidad_x = 'x' * votos

# Presentacion de resultados
print(iniciales, '(', votos, ')')
print(cantidad_x)
```

### **6. Cálculo de sueldo**

Se conoce el monto del salario actual de un empleado, el nombre del empleado y el área funcional al cual pertenece. Se pide calcular el nuevo salario del empleado sabiendo que obtuvo un incremento del 8% sobre su salario actual y un descuento de 2.5% por servicios, informando los resultados con el formato que se especifica a continuación:

**Nombre Empleado:**  xxxxxxxxx            **Nuevo Salario: $** xxx  ****

**Área Funcional:**  xxxxxxxxxxxx

**Salario Actual: $** xxxx ****

```python
# Titulo y carga de datos
print('Actualización del sueldo de un empleado')
nombre = input('Ingrese el nombre del empleado: ')
area = input('Ingrese el area funcional en la que trabaja: ')
sueldo = float(input('Ingrese el importe de su sueldo actual: '))

# Procesos
aumento = sueldo * 0.08
descuento = sueldo * 0.025
nuevo_sueldo = sueldo + aumento - descuento

# Presentacion de resultados
print('Nombre empleado:', nombre, '\\t\\tNuevo sueldo $:', nuevo_sueldo)
print('Area funcional:', area)
print('Sueldo anterior: $', sueldo)
```

### **7. Cálculo presupuestario**

En un hospital existen 3 áreas de servicios: Urgencias, Pediatría y Traumatología. El presupuesto anual del hospital se reparte de la siguiente manera:

| Área | Presupuesto |
| --- | --- |
| Urgencias | 37% |
| Pediatría | 42% |
| Traumatología | 21% |

Cargar por teclado el monto del presupuesto total del hospital, y calcular y mostrar el monto que recibirá cada área.

```python
# Titulo y carga de datos
print('Calculo presupuestario en un hospital')
presupuesto = float(input('Ingrese monto del presupuesto total: '))

# Procesos
urgencias = presupuesto * 0.37
pediatria = presupuesto * 0.42
traumatologia = presupuesto * 0.21

# Presentacion de resultados
print('Monto asignado a Urgencias:', urgencias)
print('Monto asignado a Pediatria:', pediatria)
print('Monto asignado a Traumatologia:', traumatologia)
```

### **8. Calculo Distancia de Viaje**

Un persona cautivada por los paisajes argentinos se le ocurrió la loca idea de unir los puntos mas extremos (Ushuaia y La Quiaca) en bicicleta, es decir se propuso hacer 3641.3 Km en bicicleta.

Nuestro aventurero efectivamente inició la travesía pero se accidentó y sólo recorrió *x* metros según su GPS.

Usted debe solicitar ese valor *x* e informar cuántos kilómetros y metros recorrió nuestro aventurero y qué porcentaje represento lo recorrido del total de kms a recorrer de Ushuahia a La Quiaca (para el porcentaje usted deberá realizar los cálculos en metros).

```python
print('Conversion de metros a kilimetros de viaje recorridos')
print('=' * 80)
print('\\n')

distancia = 3641.3 * 1000
x = int(input('Ingrese la cantidad de metros recorridos: '))

km = x // 1000
mts = x % 1000

porc = (x * 100) / distancia

print('El viajero recorrio ', km , ' kilometros con ', mts, ' metros')
print('Siginifica que el viajero recorrio solo un ', porc, '% del total del viaje')
```

### **9. Costos del Proyecto**

Una pequeña empresa de informática tiene que desarrollar un sistema de información y para ello tiene un presupuesto de *x* pesos para cubrir los costos de crear el sistema. Sabiendo que tiene pensado ganar al menos 17% por el proyecto, determine cuál es el valor máximo que pueden alcanzar los costos del proyecto.

```python
print('Calculo de Costos')
print('*' * 80)

presupuesto = float(input('Ingrese el monto total presupuestado: '))

ganancia = presupuesto * 0.17
costos = presupuesto - ganancia

print('Los costos del proyecto no deben exceder los $', costos)
```

### **10. Tiempos de Triatlon**

Un triatlón es una competición deportiva en que los participantes realizan tres carreras: una de natación, una ciclista y una pedestre.

Desarrollar un programa que permita ingresar el tiempo (en minutos y segundos) logrados en cada etapa por uno de los deportistas participantes.

Con esos datos determinar:

- Tiempo total de la prueba (en formato hh:mm:ss)
- Tiempo máximo y mínimo (en segundos)
- Tiempo promedio de la prueba (en segundos, redondeado a 2 decimales)

*Consejo:* convertir a segundos los horarios ingresados, para facilitar las operaciones

```python
# Titulo y carga de datos
print('TRIATLÓN')
natacion = input("Ingrese tiempo de natación (mm:ss):")
ciclismo = input("Ingrese tiempo de ciclismo (mm:ss):")
pedestre = input("Ingrese tiempo de carrera pedestre (mm:ss):")

# Procesos

# Identificar componentes y convertir a segundos
natacion_seg = int(natacion[0] + natacion[1])*60 + int(natacion[3] + natacion[4])
ciclismo_seg = int(ciclismo[0] + ciclismo[1])*60 + int(ciclismo[3] + ciclismo[4])
pedestre_seg = int(pedestre[0] + pedestre[1])*60 + int(pedestre[3] + pedestre[4])

# Calcular el total en segundos
total = natacion_seg + ciclismo_seg + pedestre_seg
horas = divmod(total,3600)
total_hh = horas[0]
minutos = divmod(horas[1],60)
total_mm = minutos[0]
total_ss = minutos[1]

#Determinar el mayor y menor tiempo
mayor_tiempo = max(natacion_seg,ciclismo_seg,pedestre_seg)
menor_tiempo = min(natacion_seg,ciclismo_seg,pedestre_seg)

#Determinar tiempo promedio y redondearlo
promedio = (natacion_seg + ciclismo_seg + pedestre_seg)/3
promedio = round(promedio,2)

# Resultados
print("\\nEstadísticas")
print("El tiempo total es: ", total_hh,":",total_mm,":",total_ss)
print("El mayor tiempo (en segundos) es: ",mayor_tiempo)
print("El menor tiempo (en segundos) es: ",menor_tiempo)
print("El tiempo promedio(en segundos) es: ",promedio)
```

### **11. Palabra enmascarada**

Desarrollar un programa que permita ingresar una palabra por teclado y la devuelva enmascarada, mostrando la primer letra y la última, pero reemplazando los caracteres intermedios por asteriscos.

Por ejemplo: si se ingresa la palabra “verde” se debe obtener “v***e”.

```python
# Titulo y carga de datos
print('Palabra enmascarada')
palabra = input('Ingrese palabra a enmascarar: ')

# Procesos

n = len(palabra)
asteriscos = "*" * (n-2)
enmascarada = palabra[0] + asteriscos + palabra[n-1]

# Resultados
print('\\nLa palabra enmascarada es:', enmascarada)
```

### **12. Calculo de Posta de Natacion**

En la disciplina olímpica una de las pruebas mas esperadas en la natacion es la posta 4x100. En esta disciplina el equipo ganador registró los siguientes tiempos en cada estilo:

- Espalda: 52 segundos 15 centésimas.
- Pecho: 1 minuto 2 segundos 75 centésimas.
- Mariposa: 59 segundos 80 centésimas.
- Libre: 48 segundos 15 centésimas.

Usted debe averiguar el tiempo total de la carrera del equipo ganador y representarlo en minutos, segundos y centésimas.

Para recordar:

- 1 minutos son 60 segundos.
- 1 segundo son 100 centesimas.

```python
print('Calculo tiempo ganador de posta 4x100')
print('*' * 80)

# tomar cada estilo y pasarlo a centésimas para sumar
espalda = 52*100 + 15
pecho = 62*100 + 75
mariposa = 59*100 + 80
crol = 48*100 + 15

total = espalda + pecho + mariposa + crol

# convertir el total a minutos, segundos y centésimas para el tiempo total
# total de centésimas por minuto:
# 1 min -> 60 seg y 1 seg -> 10 cs => 1 min = 60 * 100 = 6000 centésimas.

minutos = total // 6000
resto = total % 6000

segundos = resto // 100
centesimas = resto % 100

print('Total:', minutos, 'minutos', segundos, 'segundos y', centesimas, 'centesimas')
```

### **13. Triángulo Rectángulo**

Desarrollar un programa que, ingresando los dos catetos de un triángulo rectángulo, informe:

- Valor de la hipotenusa (redondeado a 2 decimales)
- Valor del lado mayor
- Valor del lado menor

```python
# Titulo y carga de datos
print('Triangulo rectangulo')
print()
cat1 = int(input('Ingrese uno de los catetos: '))
cat2 = int(input('Ingrese el otro cateto: '))

#Proceso
suma = pow(cat1,2) + pow(cat2,2)
hip = round(pow(suma,0.5),2)

#Resultados
print('\\nLa hipotenusa es',hip)
print('El lado mayor es',max(cat1,cat2))
print('El lado menor es',min(cat1,cat2))
```

### **14. Sumador de Áng14. Sumador de Ángulosulos14. Sumador de Ángulos**

Se desea un programa que dados 2 ángulos expresados en grados minutos y segundos, informe la suma de ambos en grados minutos y segundos.

A modo de ejemplo se agrega la siguiente gráfica:

![](file:///C:/Users/manue/AppData/Roaming/marktext/images/2022-05-10-01-08-05-image.png?msec=1652155737807)

Tener en cuenta que en el algoritmo implementado no necesariamente hay que seguir el mecanismo empírico propuesto por la imagen.

```python
# Entrada ángulo 1 como g ' "
# Entrada ángulo 2 como g ' "
# Salida Final
#   Ángulo suma como g ' "

print('*' * 30)
print('   Sumador de Ángulos')
print('*' * 30)

print('Ingrese el primer ángulo:')
grados_a1 =   int(input('\\tGrados:   '))
minutos_a1 =  int(input('\\tMinutos:  '))
segundos_a1 = int(input('\\tSegundos: '))

print('Ingrese el segundo ángulo:')
grados_a2 =   int(input('\\tGrados:   '))
minutos_a2 =  int(input('\\tMinutos:  '))
segundos_a2 = int(input('\\tSegundos: '))

print()

seg_totales_a1 = segundos_a1 + minutos_a1 * 60 + \\
                  grados_a1 * 60**2
seg_totales_a2 = segundos_a2 + minutos_a2 * 60 + grados_a2 * 60**2
# print("Segundos totales ángulo 1:", seg_totales_a1)
# print("Segundos totales ángulo 2:", seg_totales_a2)

seg_totales_suma = seg_totales_a1 + seg_totales_a2
# print("Suma total en segundos:", seg_totales_suma)

print()

grados_suma = seg_totales_suma // 60**2
segundos_restantes = seg_totales_suma % 60**2
minutos_suma = segundos_restantes // 60
segundos_suma = segundos_restantes % 60

print('*   Resultados')
#print('* El ángulo resultante: ','\\n*\\t', grados_suma, 'g ', minutos_suma, '\\' ', segundos_suma, '"')
print('* El ángulo resultante: ', \\
        '\\n*\\t', grados_suma, 'g ', \\
        minutos_suma, '\\' ', \\
        segundos_suma, '"')
print('*' * 30)
print()
print('Fin.')
print()
input("Presione Enter para finalizar...")
```

```python
# Sumador ángulos con tuplas
# Entrada ángulo 1 como g ' "
# Entrada ángulo 2 como g ' "
# Salida Final
#   Ángulo suma como g ' "

print('*' * 30)
print('   Sumador de Ángulos')
print('*' * 30)

print('Ingrese el primer ángulo:')
grados_a1 =   int(input('\\tGrados:   '))
minutos_a1 =  int(input('\\tMinutos:  '))
segundos_a1 = int(input('\\tSegundos: '))
angulo1 = (grados_a1, minutos_a1, segundos_a1)
print(angulo1)

print('Ingrese el segundo ángulo:')
grados_a2 =   int(input('\\tGrados:   '))
minutos_a2 =  int(input('\\tMinutos:  '))
segundos_a2 = int(input('\\tSegundos: '))
angulo2 = (grados_a2, minutos_a2, segundos_a2)
print(angulo2)

print()

seg_totales_a1 = angulo1[2] + angulo1[1] * 60 + \\
                  angulo1[0] * 60**2
seg_totales_a2 = angulo2[2] + angulo2[1] * 60 + angulo2[0] * 60**2
# print("Segundos totales ángulo 1:", seg_totales_a1)
# print("Segundos totales ángulo 2:", seg_totales_a2)

seg_totales_suma = seg_totales_a1 + seg_totales_a2
# print("Suma total en segundos:", seg_totales_suma)

print()

grados_suma = seg_totales_suma // 60**2
segundos_restantes = seg_totales_suma % 60**2
minutos_suma = segundos_restantes // 60
segundos_suma = segundos_restantes % 60

resultado = (grados_suma, minutos_suma, segundos_suma)
resultado_str = str(resultado[0]) + "g " + str(resultado[1]) + '\\' ' + str(resultado[2]) + '"'

print('*   Resultados')
#print('* El ángulo resultante: ','\\n*\\t', grados_suma, 'g ', minutos_suma, '\\' ', segundos_suma, '"')
print('* El ángulo resultante: ', \\
        '\\n*\\t', resultado_str)
print('*' * 30)
print()
print('Fin.')
print()
input("Presione Enter para finalizar...")
```

```python
#Sumador con tuplas II
print('SUMADOR DE ANGULOS')
print('-' * 80)

# Datos
print('Angulo 1')
grados = int(input('Ingrese grados: '))
minutos = int(input('Ingrese minutos: '))
segundos = int(input('Ingrese segundos: '))
angulo1 = grados, minutos, segundos

print('Angulo 2')
grados = int(input('Ingrese grados: '))
minutos = int(input('Ingrese minutos: '))
segundos = int(input('Ingrese segundos: '))
angulo2 = grados, minutos, segundos
print('\\nSuma de', angulo1, '+', angulo2)

# Proceso

# Convertir angulo en segundos = grados * 3600 + minutos * 60 + segundos
ang1_seg = angulo1[0] * 3600 + angulo1[1] * 60 + angulo1[2]
ang2_seg = angulo2[0] * 3600 + angulo2[1] * 60 + angulo2[2]

# Sumar los segundos
suma_seg = ang1_seg + ang2_seg
print('\\nSuma en segundos:', ang1_seg, '+', ang2_seg, '=', suma_seg)

# Convertir la suma a grados, minutos y segundos
# Segundos a grados --> division entera por 3600
# (el resto son segundos)
grados = suma_seg // 3600
resto_seg = suma_seg % 3600
# Segundos a minutos --> division entera por 60
# (el resto son segundos)
minutos = resto_seg // 60
segundos = resto_seg % 60
# Armar el ángulo resultante
angulo_suma = grados, minutos, segundos

# Resultado
print('\\nSuma sexagesimal:', angulo_suma)
```

## Ficha 04 - Estructuras condicionales

### **1. Generador de Dirección de Mail**

Se desea un programa que: solicite al usuario un nombre, un apellido y el dominio y luego, proponga una dirección de mail para el nombre y apellido ingresado de acuerdo a las siguientes reglas:

- Componer la dirección de correo de la siguiente manera:<primera letra del nombre><apellido>@<dominio>Por ejemplo para Nombre = Felipe, Apellido= Steffolani y Dominio= [frc.utn.edu.ar](http://frc.utn.edu.ar) la dirección de mail sería:fsteffolani@frc.utn.edu.ar
- Pero si la primera letra del nombre y la primera letra del apellido son la misma entonces utilizar: <nombre>.<apellido>@<dominio>Por ejemplo para Nombre= Soledad, Apellido= Steffolani y Dominio= [colegiorosarito.edu.ar](http://colegiorosarito.edu.ar) la dirección de mail sería:soledad.steffolani@colegiorosarito.edu.ar

```python
# Generador de dirección de Mail
# Entradra:
# Nombre
# Apellido
# Dominio
# Salida:
# Dirección de mail propuesta

print('#' * 30)
print('\\tGenerador de Mails')
print('#' * 30)

print('\\nIngreso de datos:')
nombre = input('\\tNombre : ')
apellido = input('\\tApellido: ')
dominio = input('\\tDominio : ')

#transformar las cadenas ingresadas en minúscula
# independientemente de cómo se ingresaron.
nombre = nombre.lower()
apellido = apellido.lower()
dominio = dominio.lower()
primera_letra_nombre = nombre[0]
primera_letra_apellido = apellido[0]

if primera_letra_apellido != primera_letra_nombre:
 mail_propuesto = primera_letra_nombre + apellido + '@' + \\
 dominio
else:
 mail_propuesto = nombre + '.' + apellido + '@' + dominio

print()
print('Mail propuesto:\\n\\t', mail_propuesto)
print('#' * 30)

input('\\nPresione enter para finalizar...')
```

### **2. Suma - División - Potencia**

Se necesita desarrollar un programa que permita calcular la suma de tres números. Si el resultado es mayor a 10 dividir por 2 (mostrar su resultado sin decimales), en caso contrario elevar el resultado al cubo.

```python
# Carga de datos
a = int(input("Ingrese un número"))
b = int(input("Ingrese un número"))
c = int(input("Ingrese un número"))

# Proceso
suma = a + b + c
if suma > 10:
    resultado = suma // 2
else:
    resultado = suma ** 3

# Presentación de resultados
print("La suma es:", suma)
print("El resultado es:", resultado)
```

### **3. Jornal de un Operario**

Se necesita desarrollar un programa para el área de recursos humanos de una empresa que permita informar el jornal de un determinado operario. Usted deberá cargar por teclado el código de turno que el operario trabajó ese día (1- representa Diurno y 2- representa Nocturno) y la cantidad de horas trabajadas.

La política de trabajo en la empresa es que los operarios de la misma pueden trabajar en el turno diurno o nocturno. Si un operario trabaja en el turno nocturno el pago es 40.60 pesos la hora, si lo hace en el turno diurno cobra 35.50 pesos la hora.

```python
print('Jornal de Operario')
print('=' * 80 , '\\n')

#Datos
turno = int(input('Ingrese el turnos del operario (1 - Diurno, 2 - Nocturno): '))
horas = int(input('Ingrese la cantidad de horas trabajadas: '))

#Proceso
if turno == 1:
    total = horas * 35.5
else:
    total = horas * 40.60

#Resultados
print('La empresa le debe pagar al operario un jornal de $', total)
```

### **4. Temperatura diaria**

Se solicita realizar un programa que permita ingresar tres temperaturas correspondientes a diferentes momentos de un día y determinar:

- Cual es el promedio de las temperaturas.
- Si existe alguna temperatura que sea mayor al promedio.

```python
import random

print('\\nIngreso de temperaturas')
temp1 = int(input("Ingrese la temperatura 1"))
temp2 = int(input("Ingrese la temperatura 2"))
temp3 = int(input("Ingrese la temperatura 3"))

# Procesos calculo del promedio
promedio = (temp1 + temp2 + temp3) / 3

# Salida de resultados
print ('El promedio de las temperaturas ingresadas fue ', promedio, ' grados')

if temp1 > promedio or temp2 > promedio or temp3 > promedio:
    print('Existe al menos una temperatura que supera al promedio')
else:
    print('Todas las temperaturas estan por debajo del promedio')
```

### **5. Tarjeta de Bingo**

Realizar un programa que genere 15 números aleatorios enteros en el rango del 1 al 100, que representaria la tarjeta de bingo de una persona. Una vez generados los números aleatorios solicitar al usuario que ingrese 3 números enteros y a partir de alli mostrar los siguientes mensajes:

- Si el usuario no marcó ninguno de los números indicarlo diciendo "El jugador tiene mala suerte, no marcó ninguna casilla"
- Caso contrario mostrar "El jugador marcó algún numero de la tarjeta".

```python
import random

print('Tarjeta de Bingo')
print("=" * 80)

print("\\nCarga de Datos")
print('-' * 80)

billete = random.randint(1,100),random.randint(1,100),random.randint(1,100),random.randint(1,100),\\
          random.randint(1,100), random.randint(1,100),random.randint(1,100),random.randint(1,100),\\
          random.randint(1,100),random.randint(1,100),random.randint(1,100),random.randint(1,100),\\
          random.randint(1,100),random.randint(1,100),random.randint(1,100)

primer_numero = int(input('Ingrese la bolilla que salio sorteada (un valor ente 1 y 100): '))
segundo_numero = int(input('Ingrese la bolilla que salio sorteada (un valor ente 1 y 100): '))
tercer_numero = int(input('Ingrese la bolilla que salio sorteada (un valor ente 1 y 100): '))

# Proceso y salida de resultados
print('La tarjeta del usuario es: ', billete)
if primer_numero in billete or segundo_numero in billete or tercer_numero in billete:
    print('El jugador marco algun numero de la tarjeta')
else:
    print('El jugador tiene mala suerte, no marco ninguna casilla')
```

### **6. Análisis de palabra**

Se pide un programa que le solicite al usuario que ingrese una palabra. Con esa palabra calcular los siguientes puntos:

- Determinar la cantidad de letras que tiene la palabra.
- Mostrar un mensaje que informe si la palabra termina en vocal.

```python
print('Analisis de Palabra')
print('=' * 80)

# Lectura de datos
palabra = input('Ingrese la palabara a analizar en mayusculas: ' )

# Proceso
largo = len(palabra)
ultima_letra = palabra[largo - 1]

termina_vocal = False
if ultima_letra == 'A' or ultima_letra == 'E' or ultima_letra == 'I' or \\
    ultima_letra == 'O' or ultima_letra == 'U':
    termina_vocal = True

# Salida
print('La palabra ingresada tiene una longitud de ', largo, ' letras')
if termina_vocal:
    print('La palabra ingresada termina en vocal')
```

### **7. Tirada de moneda**

Programar una tirada de una moneda (opciones: cara o cruz) aleatoriamente. Permitir que un jugador apueste a cara o cruz y luego informar si acertó o no con su apuesta.

```python
import random

print('Tirada de la moneda')
print('=' * 80)

caras = 'cara', 'cruz'

apuesta = int(input('Seleccion que cara desea apostar (0 Cara 1 Cruz): '))
jugada = random.choice(caras)

if jugada == caras[apuesta]:
    print('El jugador ha ganado el juego, acerto, salio', jugada)
else:
    print('El jugador ha perdido el juego salio', jugada, 'y el jugador aposto a', caras[apuesta])
```

### **8. Lanzamiento de dados**

Simular un juego en el que se lanzan dos dados.

Si ambos dados son iguales o la suma entre ellos es impar, gana el usuario. En caso contrario, gana la máquina.

```python
import random

print("Juego de Dados\\n")

dado1 = random.randrange(1, 7)
dado2 = random.randint(1, 6)

print("Dado 1:", dado1, "- Dado 2:", dado2)

suma = dado1 + dado2

if dado1 == dado2 or (suma%2) != 0:
 res = "Ganaste!"
else:
 res = "Perdiste!"

print("Resultado:", res)
```

### **9. Edad mínima**

Ingresar por teclado las edades de 3 participantes de un concurso.

Informar si todos cumplen con la edad mínima establecida para el mismo, también ingresada por teclado.

```python
#Datos
edad1 = int(input('Participante 1 - Ingrese edad: '))
edad2 = int(input('Participante 2 - Ingrese edad: '))
edad3 = int(input('Participante 3 - Ingrese edad: '))

minimo = int(input('Ingrese edad minima para participar: '))

#Proceso y resultado
if edad1 >= minimo and edad2 >= minimo and edad3 >= minimo:
    print('TODOS los participantes cumplen con la edad mínima')
else:
    print('NO TODOS los participantes cumplen con la edad mínima')
```

### **10. Terreno**

Se ingresan las medidas de frente y fondo de un terreno.

Determinar si es cuadrado o rectangular y calcular su superficie.

```python
fondo = float(input('Ingrese fondo del terreno (en metros): '))

#Proceso
if frente == fondo:
    forma = "CUADRADA"
else:
    forma = "RECTANGULAR"

superficie = round(frente * fondo,2)

#Resultados
print('El terreno tiene forma',forma,'y',superficie,'metros cuadrados de superficie')
```

### **11. Galería de arte**

Una galería de arte desea preparar un catálogo de sus cuadros más famosos.

Se realiza una prueba con tres cuadros y por cada uno se ingresa el año en que fue creado. El programa deberá:

1. Verificar si todos los cuadros son anteriores al siglo XX (El siglo XX es el siglo pasado. Se inició en el año 1901 y terminó en el año 2000).
2. Determinar si alguna de las obras fue creada en un año que se ingresa por teclado.
3. Informar la diferencia en años entre la obra más nueva y la más antigua.

```python
# Presentación e ingreso de datos
print('GALERÍA DE ARTE')
cuadro1 = int(input('Ingrese año de creación del cuadro 1: '))
cuadro2 = int(input('Ingrese año de creación del cuadro 2: '))
cuadro3 = int(input('Ingrese año de creación del cuadro 3: '))

# Proceso
# Todos los cuadros son anteriores al siglo XX?
mensaje_sxx = ' son anteriores al siglo XX'
if cuadro1 < 1900 and cuadro2 <= 1900 and cuadro3 <= 1900:
    mensaje_sxx = 'TODOS' + mensaje_sxx
else:
    mensaje_sxx = 'NO TODOS' + mensaje_sxx
# Alguno fue creado en cierto año?
anio = int(input('\\nIngrese año de creación a buscar: '))
mensaje_anio = ' hay cuadros correspondientes al año ' + str(anio)
if cuadro1 == anio or cuadro2 == anio or cuadro3 == anio:
    mensaje_anio = 'SÍ' + mensaje_anio
else:
    mensaje_anio = 'NO' + mensaje_anio
# Diferencia entre más nueva y más antigua
nueva = max(cuadro1, cuadro2, cuadro3)
antigua = min(cuadro1, cuadro2, cuadro3)
diferencia = nueva - antigua

# Resultados
print(mensaje_sxx)
print(mensaje_anio)
print('La diferencia entre la obra más nueva (', nueva, ') y la más antigua (', antigua, ') es', diferencia,'años')
```

### **12. Cartas de Truco**

Desarrollar un programa que genere al azar tres cartas simulando una mano de truco. A continuación deberá:

1. Informar si entre las cartas se encuentra el as de espadas
2. Verificar si las tres cartas son del mismo palo. Si es así, identificar cuál fue la mayor carta. En caso contrario, informarlo.

```python
import random

palos = ('Oro', 'Basto', 'Espada', 'Copa')
numeros = (1, 2, 3, 4, 5, 6, 7, 10, 11, 12)

print('CARTAS DE TRUCO')
carta1 = random.choice(numeros), random.choice(palos)
carta2 = random.choice(numeros), random.choice(palos)
carta3 = random.choice(numeros), random.choice(palos)

print(carta1, carta2, carta3)

if (carta1[0] == 1 and carta1[1] == 'Espada') \\
        or (carta2[0] == 1 and carta2[1] == 'Espada') \\
        or (carta3[0] == 1 and carta3[1] == 'Espada'):
    print('Tiene el as de espadas')
else:
    print('NO Tiene el as de espadas')

if carta1[1] == carta2[1] and carta1[1] == carta3[1]:
    may = max(carta1[0], carta2[0], carta3[0])
    print('La carta mayor es ', may, 'de', carta1[1])
else:
    print('No hay tres cartas del mismo palo')
```

### **13. Calculo de Precios con Descuento**

Una empresa nos solicito un programa que nos permita calcular los precios de los productos que vende al publicopara ello, nuestro programa debe pedir el precio unitario, la cantidad que se vendio y si se pago en efectivo o no.En base a esto determinar

1. El Precio final sin descuentos del articulo (precio unitario por cantidad)
  
2. Calcular un descuento si el usuario pago en efectivo y la cantidad vendida es superior a 10 unidades del 15% caso contrario solo aplicar un 5% de descuento
  

```python
print('Calculo de Precio de Venta')
print('=' * 60)

precio_unitario = float(input('Ingrese el precio unitario del articulo: '))
cantidad = int(input('Ingrese la cantidad que se vendio del producto: '))
es_efectivo = input('La venta del articulo, se abono en efectivo? (Responda S o N): ')

print('...Procesando')
precio = precio_unitario * cantidad

if es_efectivo == 'S' and cantidad > 10:
    descuento = precio * 0.15
else:
    descuento = (precio * 0.05)

precio_final = precio - descuento

print('\\nSalidas')
print('-' * 60, '\\n')
print('El Precio Final que se cobro del articulo fue de $', round(precio_final, 2))
print('se le aplico un ', descuento, '% de descuento a la operacion')
```

### **14. Tarifas de Peaje**

La empresa de peajes AED Pase-Pase S.R.L, festeja su séptimo aniversario y, por tal motivo, el día de hoy ofrece premios a a sus clientes.

Estos premios se calculan de la siguiente manera:

1. Cada vez que pasa un cliente, se sortea un número del 0 al 9. Si el número coincide con el último dígito de la patente del vehículo, se le cobra la tarifa promocional de $50, si no, se le cobra la tarifa estándar de $90
2. Independientemente de la tarifa que deba pagar, si el último dígito de la patente es 7, entonces recibe un descuento del 50%, en caso contrario un descuento del 10%.

Desarrolle un programa en Python que le solicite al usuario los dígitos de su patente (únicamente los dígitos), simule su paso por el peaje e indique el monto a abonar.

```python
import random

# Programa de cálculo de peajes
print('Bienvenido a Pase-Pase')
print('=' * 20)

# Ingreso de datos
digitos_patente = int(input('Ingrese dígitos:'))

# Sorteo del dígito
sorteo = random.randint(0, 9)
print('Sorteo: ', sorteo)

# Extracción del último dígito de la patente
ultimo_digito = digitos_patente % 10

# Cálculo de la tarifa
if sorteo == ultimo_digito:
    print('Tarifa Promocional')
    # Si coincide el último dígito con lo sorteado
    # Es precio promocional
    tarifa = 50
else:
    print('Tarifa Completa')
    # Si no coincide, es precio completo
    tarifa = 90

# Cálculo del descuento
if ultimo_digito == 7:
    print('Descuento del 50%')
    # Si la patente termina en 7, el
    # descuento es de 50%
    descuento = tarifa * 0.5
else:
    print('Descuento del 10%')
    # Si la patente NO termina en 7, el
    # descuento es del 10%
    descuento = tarifa * 0.1

# Monto final a pagar
monto = tarifa - descuento

# Resultados
print('=== RESULTADOS ===')
print('Debe abonar: $', monto)
```

### **1. Operaciones de orden con 3 nros.**

Realizar un programa que tome tres números, los ordene de mayor a menor, y diga si el tercero es el resto de la división de los dos primeros.

```python
 # Carga de datos
 a=int(input("Ingrese el número a: "))
 b=int(input("Ingrese el número b: "))
 c=int(input("Ingrese el número c: "))

 #Subproblema 1: Identificar el orden para cada número ingresado
 if a>b and a>c:
     may=a
     if b>c:
         med=b
         men=c
     else:
         med=c
         men=b
 elif b>c and b>a:
     may=b
     if c>a:
         med=c
         men=a
     else:
         med=a
         men=c
 else:
     may=c
     if b>a:
         med=b
         men=a
     else:
         med=a
         men=b

 #Subproblema 2: Determinar si el tercero es igual al resto de la división de los dos primeros
 if men==may%med:
     print("El tercero es igual al resto de la división de los dos primeros")
 else:
     print("El tercero NO es igual al resto de la división de los dos primeros")
```

### **2. Elecciones Presidenciales**

Según la Ley Electoral de la República Argentina, el Presidente y el Vicepresidente se eligen de acuerdo a las siguientes reglas:

Artículo 149. — Resultará electa la fórmula que obtenga más del cuarenta y cinco por ciento (45 %) de los votos afirmativos válidamente emitidos; en su defecto, aquella que hubiere obtenido el cuarenta por ciento (40 %) por lo menos de los votos afirmativos válidamente emitidos y, además, existiere una diferencia mayor de diez puntos porcentuales respecto del total de los votos afirmativos válidamente emitidos, sobre la fórmula que le sigue en número de votos.

Artículo 150. — Si ninguna fórmula alcanzare esas mayorías y diferencias de acuerdo al escrutinio ejecutado por las Juntas Electorales, y cuyo resultado único para toda la Nación será anunciado por la Asamblea Legislativa atento lo dispuesto por el artículo 120 de la presente ley, se realizará una segunda vuelta dentro de los treinta (30) días.

Artículo 151. — En la segunda vuelta participarán solamente las dos fórmulas más votadas en la primera, resultando electa la que obtenga mayor número de votos afirmativos válidamente emitidos.

Desarrollar un programa que permita ingresar, para los 3 partidos más votados: fórmula (presidente + vice) y cantidad de votos obtenidos.

Luego determinar:

- Qué fórmula obtuvo el mayor porcentaje.
- Si la fórmula resulta elegida o se requiere segunda vuelta. En este caso, indicar también quienes participan de la segunda vuelta.

```python
# Entrada de datos
p1_formula = input("Ingrese fórmula del partido 1: ")
p1_cant = int(input("Ingrese cantidad de votos partido 1: "))
p2_formula = input("Ingrese fórmula del partido 2: ")
p2_cant = int(input("Ingrese cantidad de votos partido 2: "))
p3_formula = input("Ingrese fórmula del partido 3: ")
p3_cant = int(input("Ingrese cantidad de votos partido 3: "))

# Proceso
total_votos = p1_cant + p2_cant + p3_cant
porc1 = p1_cant * 100 / total_votos
porc2 = p2_cant * 100 / total_votos
porc3 = p3_cant * 100 / total_votos

if porc1 > porc2:
    if porc2 > porc3:
        primero = porc1
        f1 = p1_formula
        segundo= porc2
        f2 = p2_formula
        tercero = porc3
        f3 = p3_formula
    else:
        tercero = porc2
        f3 = p2_formula
        if porc1 > porc3:
            primero = porc1
            f1 = p1_formula
            segundo= porc3
            f2 = p3_formula
        else:
            primero = porc3
            f1 = p3_formula
            segundo= porc1
            f2 = p1_formula
else:
    if porc1 > porc3:
        primero = porc2
        f1 = p2_formula
        segundo= porc1
        f2 = p1_formula
        tercero = porc3
        f3 = p3_formula
    else:
        tercero = porc1
        f3 = p1_formula
        if porc2 > porc3:
            primero = porc2
            f1 = p2_formula
            segundo= porc3
            f2 = p3_formula
        else:
            primero = porc3
            f1 = p3_formula
            segundo= porc2
            f2 = p2_formula

flag = False
if primero >= 45 or primero >= 40 and (primero-segundo) > 10:
    flag = True

# Salida
print("Fórmula con mayor porcentaje:", f1)

if flag == True:
    print("La fórmula resultó elegida, no hay segunda vuelta.")
else:
    print("Hay segunda vuelta. Los participantes son:")
    print("Primer puesto: ", f1)
    print("Segundo puesto: ", f2)
```

```python
#Solución con tuplas
print('Elecciones Presidenciales')
print('*' * 80)

# Datos
formula1 = input ("Ingrese fórmula lista 1: ")
votos1 = int(input("Ingrese votos lista 1: "))
formula2 = input ("Ingrese fórmula lista 2: ")
votos2 = int(input("Ingrese votos lista 2: "))
formula3 = input ("Ingrese fórmula lista 3: ")
votos3 = int(input("Ingrese votos lista 3: "))

# Procesos
#Subproblema 1: Determinar primer y segundo lugar
if votos1 > votos2 and votos1 >votos3:
    primero = formula1, votos1
    if votos2 > votos3:
        segundo = formula2, votos2
    else:
        segundo = formula3, votos3
elif votos2 > votos3:
    primero = formula2, votos2
    if votos1 > votos3:
        segundo = formula1, votos1
    else:
        segundo = formula3, votos3
else:
    primero = formula3, votos3
    if votos1 > votos2:
        segundo = formula1, votos1
    else:
        segundo = formula2, votos2

#Subproblema 2: Definir el resultado de la elección
total = votos1 + votos2 + votos3
porcentaje1 = primero[1] * 100 / total
if porcentaje1 > 45:
    resultado = 'Ganó con más del 45% de los votos ' + primero[0]
else:
    diferencia = porcentaje1 - (segundo[1] * 100 / total)
    if porcentaje1 >= 40 and diferencia >= 10:
        resultado = 'Ganó con 40%: ' + primero[0] + ' por diferencia de más de 10 puntos con ' + segundo[0]
    else:
        resultado = "Segunda vuelta entre: " + primero[0] + " y " + segundo[0]

# Resultados
print('*' * 80)
print(resultado)
```

### **3. Mantenimiento Informático**

El Área de Mantenimiento de un laboratorio informático nos ha solicitado el desarrollo de un programa que facilite la gestión de las tareas realizadas en el día.

El usuario debe ingresar de tres equipos informáticos (PC) los siguientes datos: número de identificación de la PC, tiempo de reparación (expresado en minutos) y la causa de mantenimiento (1- Problema de Hardware 2-Problema de Software)

Los requerimientos funcionales son:

a) ¿Cuál es el tiempo total de las tareas de mantenimiento?

b) ¿Cuál es la PC (Número de identificación) que tuvo mayor tiempo en tareas de mantenimiento?

c) Tiempo promedio de tareas de mantenimiento.

d) Informar con un mensaje si todas las PC (Número de identificación) que se les ha realizado mantenimiento tuvieron problemas de Hardware.

```python
print('Mantenimiento informatico')
print('='* 80)

numero_pc = int(input('Ingrese numero de identificacion de la pc: '))
tiempo_reparacion = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa = int(input('Ingrese la causa del mantemiento (1 - Hardware, 2 - Software'))
equipo1 = numero_pc, tiempo_reparacion, causa

numero_pc = int(input('Ingrese numero de identificacion de la pc: '))
tiempo_reparacion = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa = int(input('Ingrese la causa del mantemiento (1 - Hardware, 2 - Software'))
equipo2 = numero_pc, tiempo_reparacion, causa

numero_pc = int(input('Ingrese numero de identificacion de la pc: '))
tiempo_reparacion = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa = int(input('Ingrese la causa del mantemiento (1 - Hardware, 2 - Software'))
equipo3 = numero_pc, tiempo_reparacion, causa

# procesos

total_mant = equipo1[1] + equipo2[1] + equipo3[1]
prom_mant = total_mant / 3

if equipo1[1] > equipo2[2] and equipo1[1] >  equipo3[1]:
    mayor = equipo1
else:
    if equipo2[1] > equipo3[2]:
        mayor = equipo2
    else:
        mayor = equipo3

mant_por_hardware = False
if equipo1[2] == 1 and equipo2[2] == 1 and equipo3[2] == 1:
    mant_por_hardware = True

# Salidas
print('El tiempo total de reparacion de las tres PC fue de', total_mant,'minutos')
print('La PC con mayor tiempo de reparacion fue la numero', mayor[0])
print('El tiempo promedio de reparacion fue de', prom_mant, 'minutos')

if mant_por_hardware:
    print('Todas las PC recibiron mantenimiento por problemas de harware')
else:
    print('Las PC recibieron distintos tipos de mantenimiento')
```

```python
# Solución con tuplas
print('Mantenimiento informatico')
print('='* 80)

#Datos
numero1 = int(input('Ingrese numero de identificacion de la primera PC: '))
tiempo1 = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa1 = int(input('Ingrese la causa del mantemiento (1=Hardware / 2=Software): '))

numero2 = int(input('Ingrese numero de identificacion de la segunda PC: '))
tiempo2 = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa2 = int(input('Ingrese la causa del mantemiento (1=Hardware / 2=Software): '))

numero3 = int(input('Ingrese numero de identificacion de la tercera PC: '))
tiempo3 = int(input('Ingrese el tiempo en minutos de reparacion: '))
causa3 = int(input('Ingrese la causa del mantemiento (1=Hardware / 2=Software): '))

#Proceso
tiempo_total = tiempo1 + tiempo2 + tiempo3

if tiempo1 > tiempo2 and tiempo1 > tiempo3:
    mayor = numero1,tiempo1
else:
    if tiempo2 > tiempo3:
        mayor = numero2, tiempo2
    else:
        mayor = numero3, tiempo3

promedio = round(tiempo_total / 3,2)

if causa1 == 1 and causa2 == 1 and causa3 == 1:
    todos_hardare = True
else:
    todos_hardare = False

# Salidas
print()
print('El tiempo total de reparacion de las tres PC fue de', tiempo_total,'minutos')
print('La PC con mayor tiempo de reparacion fue la numero', mayor[0],'con',mayor[1],'minutos')
print('El tiempo promedio de reparacion fue de', promedio, 'minutos')

if todos_hardare:
    print('Todas las PC recibiron mantenimiento por problemas de hardware')
else:
    print('Las PC recibieron distintos tipos de mantenimiento')
```

### **4. Observatorio meteorológico**

Un observatorio meteorológico ha tomado el registro de temperaturas en distintos momentos del día. Se solicita el desarrollo de un programa que facilite información estadísticas de ellas.

El usuario debe ingresar cuatro valores de temperatura (considerar que son valores enteros).

Los requerimientos funcionales son:

a) Promedio de temperatura diaria.

b) Temperatura máxima.

c) Temperatura mínima.

d) Informar con un mensaje si algunas de las temperaturas supera a la temperatura promedio.

```python
print('Observatorio Metereologico')
print('=' * 80)

#entrada de datos
temp1 = int(input('Ingrese la primer temperatura del dia: '))
temp2 = int(input('Ingrese la segunda temperatura del dia: '))
temp3 = int(input('Ingrese la tercer temperatura del dia: '))
temp4 = int(input('Ingrese la cuarta temperatura del dia: '))

# Procesos

promedio = (temp1 + temp2 + temp3 + temp4) / 4

if temp1 > temp2 and temp1 > temp3 and temp1 > temp4:
    mayor = temp1
else:
    if temp2 > temp3 and temp2 > temp4:
        mayor = temp2
    else:
        if temp3 > temp4:
            mayor = temp3
        else:
            mayor = temp4

if temp1 < temp2 and temp1 < temp3 and temp1 < temp4:
    menor = temp1
else:
    if temp2 < temp3 and temp2 < temp4:
        menor = temp2
    else:
        if temp3 < temp4:
            menor = temp3
        else:
            menor = temp4

supera_promedio = False
if temp1 > promedio or temp2 > promedio or temp3 > promedio or temp4 > promedio:
    supera_promedio = True

#Salidas
print('La temperatura promedio del dia fue de', promedio, 'grados')
print('La temperatura minima fue de', menor,'grados')
print('La temperatura maxima fue de', mayor,'grados')
if supera_promedio:
    print('Algunas de las temperaturas tomadas supero a la temperatura promedio del dia')
```

### **5. Menú de Opciones Básico**

Diseñar un programa que según la opción ingresada por el usuario permita realizar las siguientes operaciones:

- Si la opción es 1 mostrar la superficie de un triángulo. Para calcular la superficie debe usarse la fórmula de Herón:

![](file:///C:/Users/manue/AppData/Roaming/marktext/images/2022-05-10-01-22-27-image.png?msec=1652156558435)

- Si la opción ingresada es 2 mostrar el perímetro del triángulo.
- Si la opción ingresada es 3 informar la longitud del lado menor.
- Si la opción ingresada no fue ni 1, 2 o 3 informar un mensaje de error.

Para ello usted deberá ingresar por teclado el número de opción y el valor de los tres lados del triángulo.

```python
print('Menu de Opciones')
print('-' * 80)
print('1 - Calcular superficie del triangulo')
print('2 - Calcular perimetro del triangulo')
print('3 - Buscar menor lado del triangulo')
opcion = int(input('Ingrese su opcion: '))

if 1 <= opcion <= 3:

    lado1 = int(input('Ingrese el primer lado del triangulo'))
    lado2 = int(input('Ingrese el segundo lado del triangulo'))
    lado3 = int(input('Ingrese el tercer lado del triangulo'))

    if opcion == 1:
        s = (lado1 + lado2 + lado3) / 2
        superficie = (s * (s - lado1) * (s - lado2) * (s - lado3)) ** 0.5
        print('La superficie del triangulo es:', superficie)
    elif opcion == 2:
        perimetro = lado1 + lado2 + lado3
        print('El perimetro de un triangulo es', perimetro)
    elif opcion == 3:
        menor = min(lado1, lado2, lado3)
        print('El menor de los lados es', menor)
else:
    print('Selecciono una opcion erronea!!')
```

### **6. Institución Educativa**

Una institución educativa necesita un programa que facilite la gestión de cupos de los cursos de primer grado. Ingresar tres grados. De cada grado se ingresa el código de identificación (Ejemplo 1A, 1B, ...) y la cantidad de niños y de niñas y cupo máximo (que es el mismo para los tres cursos).

Los requerimientos funcionales son:

a)  Código de identificación del curso que tenga menos alumnos inscriptos.

b)  Porcentaje de niñas de cada curso.

c)  Porcentaje de niños de cada curso.

d)  Promedio general de alumnos.

e) Si algunos de los tres grados supera el cupo máximo informar un mensaje la necesidad de apertura de una nueva división.

```python
print('Administracion cupos grados de escuela')
print('=' * 80)

# entrada de datos
cupo = int(input('Ingrese el cupo de alumnos maximo a considerar: '))

identificacion = input('Ingrese la identificacion del grado: ')
ninos = int(input('Ingrese la cantidad de niños inscriptos al grado: '))
ninas = int(input('Ingrese la cantidad de niñas inscriptos al grado: '))
grado1 = identificacion, ninos, ninas,cupo, (ninos + ninas)

identificacion = input('Ingrese la identificacion de otro grado: ')
ninos = int(input('Ingrese la cantidad de niños inscriptos al grado: '))
ninas = int(input('Ingrese la cantidad de niñas inscriptos al grado: '))
grado2 = identificacion, ninos, ninas,cupo, (ninos + ninas)

identificacion = input('Ingrese la identificacion del ultimo grado: ')
ninos = int(input('Ingrese la cantidad de niños inscriptos al grado: '))
ninas = int(input('Ingrese la cantidad de niñas inscriptos al grado: '))
grado3 = identificacion, ninos, ninas,cupo, (ninos + ninas)

# procesos

if grado1[4] < grado2[4] and grado1[4] < grado3[4]:
    menor = grado1
else:
    if grado2[4] < grado3[4]:
        menor = grado2
    else:
        menor = grado3

porc_fem_grado1 = grado1[2] * 100 / grado1[4]
porc_fem_grado2 = grado2[2] * 100 / grado2[4]
porc_fem_grado3 = grado3[2] * 100 / grado3[4]

porc_masc_grado1 = grado1[1] * 100 / grado1[4]
porc_masc_grado2 = grado2[1] * 100 / grado2[4]
porc_masc_grado3 = grado3[1] * 100 / grado3[4]

promedio = (grado1[4] + grado2[4] + grado3[4]) // 4

supera = False
if grado1[4] > grado1[3] or grado2[4] > grado2[3] or grado3[4] > grado3[3]:
    supera = True

# salida
print('El grado con menor cantidad de inscriptos es', menor[0])
print('Hay un ', porc_fem_grado1, '% de niñas inscriptas en un grado')
print('Hay un ', porc_fem_grado2, '% de niñas inscriptas en otro grado')
print('Hay un ', porc_fem_grado3, '% de niñas inscriptas en el ultimo grado')
print('Hay un ', porc_masc_grado1, '% de niños inscriptas en un grado')
print('Hay un ', porc_masc_grado2, '% de niños inscriptas en otro grado')
print('Hay un ', porc_masc_grado3, '% de niños inscriptas en el ultimo grado')

print('El promedio general de alumnos inscriptos fue de ', promedio, 'alumnos')
if supera:
    print('Algun grado desbordo el cupo maximo permitido, debe abrirse otra division')
```

### **7. Juego de Dados: Pares e Impares**

Desarrollar un programa para simular un juego de dados con las siguientes reglas:

- Participan 3 jugadores: el campeón y 2 retadores.
- Antes de comenzar el juego, se debe ingresar el récord del campeón.
- En las dos primeras rondas, compiten sólo los retadores: se lanzan 2 dados. Si la suma de ambos es impar, gana el retador 1; si no, gana el retador 2.
  - Primera ronda: el ganador obtiene tantos puntos como indica la suma de los dados
  - Segunda ronda: a los puntos de la primera ronda, el ganador suma tantos puntos como indique el dado de mayor valor, y al perdedor se le restan tantos puntos como indique el dado de menor valor
- Ronda final: se suma a la competencia el campeón actual, que participa con un puntaje equivalente a su récord.

Se pide:

- Mostrar en cada ronda el valor de los dados y los puntajes de cada retador.
- Si ninguno de los retadores supera al campeón, este mantiene su puesto. En caso contrario, el que obtenga mayor puntaje será el ganador.
- Al terminar, informar si alguno de los retadores llegó a tener más puntos que el record.

```python
import random

print('Pares e Impares')
print('*' * 80)

# Antes de comenzar el juego, se debe ingresar el récord del campeón (y prever una bandera para detectar si se supera
campeon = int(input('Ingrese record del campeon: '))
superado = False

# Primera ronda entre los retadores:
dado1 = random.randint(1, 6)
dado2 = random.randint(1, 6)
suma = dado1 + dado2
print("Primera ronda: Los dados suman:", suma, "(", dado1, "y", dado2, ")")
if suma % 2 != 0:
    retador1 = suma
    retador2 = 0
else:
    retador1 = 0
    retador2 = suma
print("Retador 1:", retador1, "vs Retador 2:", retador2)
# Superaron el record?
if retador1 > campeon or retador2 > campeon:
    superado = True

# Segunda ronda entre los retadores
dado1 = random.randint(1, 6)
dado2 = random.randint(1, 6)
suma = dado1 + dado2
print("Segunda ronda: Los dados suman:", suma, "(", dado1, "y", dado2, ")")
if suma % 2 != 0:
    retador1 = retador1 + max(dado1, dado2)
    retador2 = retador2 - min(dado1, dado2)
else:
    retador2 = retador2 + max(dado1, dado2)
    retador1 = retador1 - min(dado1, dado2)
print("Retador 1:", retador1, "vs Retador 2:", retador2)
# Superaron el record?
if retador1 > campeon or retador2 > campeon:
    superado = True

# Ronda final
if campeon >= retador1 and campeon >= retador2:
    resultado = "El Campeon retiene su titulo"
elif retador1 > retador2:
    resultado = "Retador 1 es el nuevo campeon!"
elif retador2 > retador1:
    resultado = "Retador 2 es el nuevo campeon!"
else:
    resultado = "Retador 1 y Retador 2 empataron!"

if superado == True:
    print('El record fue superado durante el juego')
else:
    print('El record NO fue superado durante el juego')

# Resultado
print('*' * 80)
print('[' * 5, resultado, ']' * 5)
```

### **8. Juego del Punto**

La idea general del ***Juego del Punto***, es lograr el máximo puntaje en 4(cuatro) vueltas de lanzamiento de 3 dados, y a continuación enumeramos las reglas en base a las cuales se obtiene puntaje:

1.) Cada jugador dispone de 4(cuatro) tiradas o lanzamientos para lograr su objetivo, el programa solo deberá simular de a una tirada por vez.

2.) En cada tirada se lanzan 3(tres) dados. *Sólo suman puntaje los dados que salgan con un punto en el centro (esto es: el 1, el 3 y el 5)* (y de allí el nombre del juego)*.* El puntaje de la tirada se calcula sumando el aporte de cada dado, de acuerdo a  las siguientes  pautas:

- Si sale el 1, se suma 1(un) punto (el único que muestra el dado).
- Si sale el 3, se suman 2(dos) puntos (porque a los costados del punto central hay dos puntos).
- Si sale el 5, se suman 4(cuatro) puntos (porque en este caso, hay cuatro puntos a los costados del central).
- Si sale un número par (2, 4 o 6) no se suma ningún punto (porque ese dado no tiene punto central).

3.) Si en alguna de las tiradas el jugador saca *tres números pares iguales*, entonces el jugador duplicará los puntos finales que haya sumado al terminar sus cuatro lanzamientos.

**Se pide:** que en base a todo lo indicado, se genere un programa que simule 1 tirada de los 3 dados y luego habiendo solicitado al usuario que cargue su puntaje previo, informe su puntaje acumulado en el caso de haber obtenido puntos, su puntaje previo y el mensaje de que duplica puntos si salieron los 3 pares o simplemente su puntaje previo si no sumó ningún punto.

```python
# Importamos random para la simulación de la tirada de dados
import random

# Encabezado de la consola
print('*' * 40)
print('Simulador de tirada del Juego del Punto')
print('*' * 40)

# Solicitamos la carga de los puntos previos
puntos_previos = int(input('\\nIngrese sus puntos previos: '))

# Simulamos la tirada de dados e informamos cual fue el valor que salió
d1 = random.randint(1,6)
print('Dado 1:', d1)

d2 = random.randint(1,6)
print('Dado 2:', d2)

d3 = random.randint(1,6)
print('Dado 3:', d3)

# Definimos banderas y acumuladores
duplica = False
puntos = 0

# Primero evaluamos si duplica,
# ya que de ser verdad el resto de la evaluación no hace falta.
if (d1 % 2) == 0 and d1 == d2 and d1 == d3:
    duplica = True
else:
# Evaluamos los puntos obtenidos para el dado 1
    if d1 == 1:
        puntos += 1
    else:
        if d1 == 3:
            puntos += 2
        else:
            if d1 == 5:
                puntos += 4
# Evaluamos los puntos obtenidos para el dado 2
    if d2 == 1:
        puntos += 1
    elif d2 == 3:
        puntos += 2
    elif d2 == 5:
        puntos += 4
# Evaluamos los puntos obtenidos para el dado 3
    if d3 == 1:
        puntos += 1
    elif d3 == 3:
        puntos += 2
    elif d3 == 5:
        puntos += 4

# Mostramos los resultados
puntos_previos += puntos
print('\\n Puntos obtenidos en esta tirada:', puntos)
print('\\n Puntos totales acumulados:', puntos_previos)

if duplica:
    print('\\n Suertudo!!! duplica puntaje')

print('\\n\\n Fin!')
```

### **9. ¿Piedra, Papel o Tijera?**

Desarrollar un programa que permita al usuario jugar contra la computadora el clásico “Piedra, Papel o Tijera” y determine cuál de ellos es el ganador.

Las reglas son:

- La piedra aplasta (o rompe) la tijera. (Gana la piedra).
- La tijera corta el papel. (Gana la tijera).
- El papel envuelve la piedra. (Gana el papel)
- Si los dos jugadores eligen el mismo elemento, empatan.

```python
# Solución realizada en clase al problema Piedra/Papel/Tijera

# import de librerías
import random

# creación de variables internas
elementos = ('PIEDRA','PAPEL','TIJERA')

#Titulos
print('Piedra, Papel o Tijera - Humano vs. Máquina')
print('*' * 80)

#Ingreso de datos
opcion = int(input('Ingrese (0->PIEDRA, 1->PAPEL o 2->TIJERA): '))
humano = elementos[opcion]
print('\\n\\nHumano elige',humano)

# Selección de la máquina
maquina = random.choice(elementos)
print('\\n\\nMáquina elige',maquina)

#Proceso
if humano == maquina:
 resultado= 'Empataron'
else:
 if (maquina=='PIEDRA' and humano=='TIJERA') \\
 or (maquina == 'PAPEL' and humano == 'PIEDRA') \\
 or (maquina == 'TIJERA' and humano == 'PAPEL'):
 resultado = 'Gana MAQUINA'
 else:
 resultado = 'Gana HUMANO'

#Mostrar resultados
print('\\n\\n¡',resultado,'!')
```

### **10. Impuesto Automotor**

Crear un programa que permita calcular los impuestos que debe pagar un auto, conociendo su modelo (año de fabricación) y tipo (P: Particular/T: Taxi/R: Remis). Para calcular los impuestos, tener en cuenta que:

a. Los autos particulares de menos de 10 años de antigüedad pagan $200, entre 10 y 20 años pagan $150 y no pagan impuestos los que tienen más de 20 años.

b. Los taxis pagan impuestos como auto particular, más $150 por la licencia de taxi.

c. Los remises pagan $100 por cada año de antigüedad de su vehículo.

```python
#Cargar los datos
modelo = int(input("Ingrese año de fabricación: "))
tipo = input("Ingrese tipo (P/T/R): ")
antig = 2020 - modelo

#Determinar impuestos
if tipo == "P" or tipo == "T":
    if antig < 10:
        impuestos = 200
    elif antig > 20:
        impuestos = 150
    else:
        impuestos = 0
    if tipo == "T":
        impuestos = impuestos + 150
else:
    impuestos = 100 * antig

print ("El vehículo debe abonar $ ", impuestos)
```

### **11. Calculo de Regularidad**

La facultad pide un simple programa que pida las tres notas de un alumno en cualquier materia y mostrar si el alumno esta libre, regular o promocionado. Las tres notas son los dos parciales mas la nota de prácticos y las condiciones de regularidad están descriptas a continuacón:

- El promedio menor a 4 el alumno esta libre.
- El promedio comprendido entre 4 y 8 el alumno esta regular.
- El promedio mayor a 8 el alumno está promocionado.

```python
print('Calculo de regularidad de un alumno')
print('*' * 80)

# Ingreso de datos
primer_parcial = float(input('Ingrese la nota del primer parcial: '))
segundo_parcial = float(input('Ingrese la nota del segundo parcial: '))
practicos = float(input('Ingrese el promedio de los trabajos practicos: '))

# Procesos
promedio = (primer_parcial + segundo_parcial + practicos) / 3

condicion = ''
if promedio < 4:
    condicion = 'Alumno Libre'
elif promedio >= 4 and promedio <= 8:
    condicion = 'Alumno Regular'
else:
    condicion = 'Alumno Promocionado'

# Salidas
print('El promedio del alumno fue de', round(promedio, 2),
      'y su condicion es', condicion)
```

### **12. Punto en el plano**

Se pide realizar un programa que ingresando el valor x e y de un punto determine a que cuadrante pertenece en el sistemas de coordenadas.

```python
print('Calculo del cuadrante de un punto')
print('*' * 80)

# Ingreso de datos
x = int(input('Ingrese la coordenada x del punto: '))
y = int(input('Ingrese la coordenada y del punto: '))

# Procesos
if x == 0 or y == 0:
    cuadrante = 'alguno de los ejes o el origen'
elif x > 0 and y > 0:
    cuadrante = 'Primer Cuadrante'
elif x > 0 and y < 0:
        cuadrante = 'Cuarto Cuadrante'
elif x < 0 and y > 0:
    cuadrante = 'Segundo Cuadrante'
elif x < 0 and y < 0:
    cuadrante = 'Tercer Cuadrante'

# Salida
print('El punto (',x,",",y,') se encuentra ubicado en:', cuadrante)
```

### **13. Postulantes a un empleo**

Se tienen los datos de tres postulantes a un empleo a los que se les realizó un test de capacitación. Por cada postulante se tiene la siguiente información: nombre del postulante, cantidad total de preguntas que se le realizaron y cantidad de preguntas que contestó correctamente.

Se pide confeccionar un programa que lea los datos de los tres postulantes, informe el nivel de cada uno según los criterios de aprobación que se indican mas abajo, e indique finalmente el nombre del postulante que ganó el puesto. Los criterios de aprobación son los siguientes, en función del *porcentaje de respuestas correctas* sobre el total de preguntas realizadas a cada postulante:

- Nivel Superior: Porcentaje >= 90%
- Nivel Medio: 75% <= Porcentaje < 90%
- Nivel Regular: 50% <= Porcentaje < 75%
- Fuera de Nivel: Porcentaje < 50%

```python
print('Postulantes a un empleo')
print('=' * 80, '\\n')

# Entrada
print('Lectura de Datos del primer postulante')
nombre1 = input('Ingrese el nombre: ')
preguntas1 = int(input('Ingrese cuantas preguntas se le realizaron: '))
respondidas1 = int(input('Ingrese la cantidad de preguntas que respondio: '))

print('\\nLectura de Datos del segundo postulante')
nombre2 = input('Ingrese el nombre: ')
preguntas2 = int(input('Ingrese cuantas preguntas se le realizaron: '))
respondidas2 = int(input('Ingrese la cantidad de preguntas que respondio: '))

print('\\nLectura de Datos del tercer postulante')
nombre3 = input('Ingrese el nombre: ')
preguntas3 = int(input('Ingrese cuantas preguntas se le realizaron: '))
respondidas3 = int(input('Ingrese la cantidad de preguntas que respondio: '))

# Procesos
porcentaje1 = respondidas1 / preguntas1 * 100
porcentaje2 = respondidas2 / preguntas2 * 100
porcentaje3 = respondidas3 / preguntas3 * 100

# Determinar nivel en base al porcentaje de cada postulante
if porcentaje1 > 90:
    nivel1 = 'Nivel superior'
elif 75 <= porcentaje1 < 90:
    nivel1 = 'Nivel Medio'
elif 50 <= porcentaje1 < 75:
    nivel1 = 'Nivel Regular'
else:
    nivel1 = 'Fuera de Nivel'

if porcentaje2 > 90:
    nivel2 = 'Nivel superior'
elif 75 <= porcentaje2 < 90:
    nivel2 = 'Nivel Medio'
elif 50 <= porcentaje2 < 75:
    nivel2 = 'Nivel Regular'
else:
    nivel2 = 'Fuera de Nivel'

if porcentaje3 > 90:
    nivel3 = 'Nivel superior'
elif 75 <= porcentaje3 < 90:
    nivel3 = 'Nivel Medio'
elif 50 <= porcentaje3 < 75:
    nivel3 = 'Nivel Regular'
else:
    nivel3 = 'Fuera de Nivel'

if porcentaje1 > porcentaje2 and porcentaje1 > porcentaje3:
    mayor_nombre = nombre1
    mayor_nivel = nivel1
    mayor_porcentaje = porcentaje1
elif porcentaje2 > porcentaje3:
    mayor_nombre = nombre2
    mayor_nivel = nivel2
    mayor_porcentaje = porcentaje2
else:
    mayor_nombre = nombre3
    mayor_nivel = nivel3
    mayor_porcentaje = porcentaje3

# Presentación de resultados
print('El Postulante', nombre1, 'obtuvo el nivel', nivel1)
print('El Postulante', nombre2, 'obtuvo el nivel', nivel2)
print('El Postulante', nombre3, 'obtuvo el nivel', nivel3)

print('El postulante que obtuvo el puesto es', mayor_nombre, 'al responder \\
correctamente el', mayor_porcentaje, '% obteniendo un nivel', mayor_nivel)
```

### **14. Comercio**

Un comerciante tiene a la venta 3 tipos de artículos principales. Conociendo la cantidad vendida de cada artículo y el precio unitario de cada artículo, hacer un programa que determine cuál fue el producto que realizó el mayor aporte en los ingresos y el porcentaje que dicho aporte significa en el ingreso absoluto de los 3 artículos sumados. Ese porcentaje se calcula así:

Absoluto ____________ 100%

Mayor aporte _________ x %

Por lo tanto: x = mayor aporte * 100 / absoluto

```python
print('Comercio')
print('Carga de Articulos Vendidos')
print('=' * 40)

print('Datos del primer Articulo')
print('_' * 40)
nombre1 = input('Ingrese el nombre del articulo: ')
cantidad1 = int(input('Ingrese la cantidad vendida del articulo: '))
precio1 = float(input('Ingrese el precio unitario del articulo: '))

print('\\n')
print('Datos del segundo Articulo')
print('_' * 40)
nombre2 = input('Ingrese el nombre del articulo: ')
cantidad2 = int(input('Ingrese la cantidad vendida del articulo: '))
precio2 = float(input('Ingrese el precio unitario del articulo: '))

print('\\n')
print('Datos del tercer Articulo')
print('_' * 40)
nombre3 = input('Ingrese el nombre del articulo: ')
cantidad3 = int(input('Ingrese la cantidad vendida del articulo: '))
precio3 = float(input('Ingrese el precio unitario del articulo: '))

# Calculo de la ganancia obtenida por cada tipo de articulo
ganancia1 = cantidad1 * precio1
ganancia2 = cantidad2 * precio2
ganancia3 = cantidad3 * precio3

# Busqueda de la mayor ganancia
if ganancia1 > ganancia2 and ganancia1 > ganancia3:
    mayor = nombre1, ganancia1
elif ganancia2 > ganancia3:
    mayor = nombre2, ganancia2
else:
    mayor = nombre3, ganancia3

# Salida con calculo de porcentajes
print('El articulo que mayor aporte realizo fue', mayor[0],
      'con una ganancia de $', mayor[1])

total = ganancia1 + ganancia2 + ganancia3
porcentaje = mayor[1] * 100 / total
print('y representa el', round(porcentaje, 2), '% del total de ingresos')
```

### **15. Pago a un Proveedor**

Un comercio necesita informar el importe final a pagar a un determinado proveedor. Para ello debe ingresar la categoría (que puede ser categoría 'A' o 'B') y el importe original a abonar.

Considerar las siguientes condiciones para el cálculo del importe final a pagar:

- Si el cliente es categoría A y el monto a pagar supera a los 1000 pesos debe aplicarse un descuento del 5%.
- Si el cliente es categoría B y el importe a pagar oscila entre 1500 y 2500 pesos debe aplicarse un descuento del 2%.

Para ambas categorías en caso de no cumplirse las condiciones especificadas no se aplicará ningún tipo de descuento sobre el importe que se le debe abonar.

```python
print('Pago a proveedores')
print('=' * 80)

print('\\nCarga de Datos del Proveedor')
categoria = input('Ingrese la categoria del proveedor (A o B): ')
importe = float(input('Ingrese el importe que se le debe pagar al proveedor: '))

# Proceso

if categoria == 'A' and importe > 1000:
    total = importe - importe * 0.05
elif categoria == 'B' and 1500 <= importe <= 2500:
    total = importe - importe * 0.02
else:
    total = importe

# Salidas
print("El importe total al proveedor es de $", total)
```

### **16. Raíces de un polinomio de segundo grado**

Realizar un programa que permita calcular las raíces de un polinomio de segundo grado y mostrar un mensaje indicando si son reales o imaginarias. Si son reales distintas, mostrar sus dos valores, si son reales iguales, mostrar solo una.

*Ayudita: A partir del discriminante Δ, es posible determinar la naturaleza de las raíces de la ecuación (considerando coeficientes reales) y se pueden presentar 3 situaciones:*

- *Si Δ es negativo, ambas raíces son números complejos.*
- *Si Δ es igual a cero, existen dos raíces reales e iguales, por lo tanto hay una solución.*
- *Si Δ es positivo, ambas raíces son reales y distintas.*

```python
# Titulo y carga de datos
print('Ejercicio: Raíces de un Polinomio de Segundo Grado ')
a = float(input('Ingrese el valor de la constante a del polinomio: '))
b = float(input('Ingrese el valor de la constante b del polinomio: '))
c = float(input('Ingrese el valor de la constante c del polinomio: '))

# Procesos
discriminante = b ** 2 - 4 * a * c
mensaje="****************** Resultado ******************\\n"
if discriminante==0:
    solucion=(-b+ (b ** 2 - 4 * a * c)**0.5)/2*a
    mensaje+="Existen dos raíces reales e iguales, por lo tanto hay una solución.\\n Solucion: "+str(solucion)
elif discriminante>0:
    solucion1=(-b+ (b ** 2 - 4 * a * c)**0.5)/2*a
    solucion2=(-b- (b ** 2 - 4 * a * c)**0.5)/2*a
    mensaje+="Ambas raíces son reales y distintas, por lo tanto hay dos soluciones.\\n Solucion 1: "+str(solucion1)+"\\n Solucion 2: "+str(solucion2)
else:
    mensaje+="Ambas raíces son números complejos."

# Presentacion de Resultados
print(mensaje)
```

### **17. Índice de Masa Corporal**

Realice un programa que le permita calcular el Índice de Masa Corporal (IMC) de una persona en función de su peso (en kgs.) y su altura (en mts.), sabiendo que el IMC es igual al peso dividido la altura al cuadrado. En función del valor del IMC, el programa debe mostrar por pantalla el diagnóstico resultante del análisis del índice según las siguientes situaciones:

- Si el IMC es menor o igual a 16: “Necesita asistencia de un médico, los riesgos para su salud son muy altos”.
- Si el IMC es menor o igual a 17: "Usted tiene infrapeso, aliméntese más".
- Si el IMC es menor o igual a 18: "Usted tiene bajo peso, aliméntese mejor".
- Si el IMC es mayor a 18 y menor o igual a 26: "Usted tiene un peso saludable, continúe así!".
- Si el IMC es mayor a 26 y menor a 30: "Tiene sobrepeso de grado I, hoy es un buen día para empezar a hacer ejercicios".
- Si el IMC es mayor o igual a 30 y menor o igual a 35: "Tiene obesidad de grado II, necesita el apoyo de un plan nutricional".
- Si el IMC es mayor a 35 y menor o igual a 40: "Tiene obesidad grado III (pre-mórbida), consulte con su médico los riesgos para su salud".
- Si el IMC es mayor a 40: "Usted tiene obesidad de grado IV (mórbida), los riesgos para su salud son muy altos, consulte con su médico a la brevedad”.

```python
print("Ejercicio de IMC")

# Titulo y carga de datos
peso=float(input("Ingrese su peso expresado en Kg.:"))
altura=float(input("Ingrese su altura expresada en mts.:"))
mensaje='*' * 50
imc=round(peso/altura**2,2)
mensaje+="\\nResultado de IMC: "+str(imc)+"\\n"
mensaje+='*' * 50+"\\n"

# Procesos
if imc<=16:
    mensaje += "Necesita asistencia de un medico, los riesgos para su salud son muy altos."
elif imc<=17:
    mensaje += "Usted tiene infrapeso, alimentese mas."
elif imc<=18:
    mensaje += "Usted tiene bajo peso, alimentese mejor."
elif imc>18 and imc<=26:
    mensaje += "Usted tiene un peso saludable, continue asi!."
elif imc>26 and imc<30:
    mensaje += "Tiene sobrepeso de grado I, hoy es un buen día para empezar a hacer ejercicios."
elif imc>=30 and imc<=35:
    mensaje += "Tiene obesidad de grado II, necesita el apoyo de un plan nutricional."
elif imc>35 and imc<=40:
    mensaje += "Tiene obesidad grado III (pre-morbida), consulte con su medico los riesgos para su salud."
else:
    mensaje += "Usted tiene obesidad de grado IV (morbida), los riesgos para su salud son muy altos, consulte con su medico a la brevedad."

# Presentacion de Resultados
print(mensaje)
```

### **18. Lluvias**

En una localidad nos piden que realicemos un análisis de las lluvias caídas en un trimestre (3 cantidades).

Para ello se debe ingresar por teclado la cantidad de milímetros caídos por mes y con dichos datos resolver lo siguiente:

- Promedio de milímetros caídos.
- Cantidad de meses con más o igual lluvia que el promedio.
- Mes con menos lluvias en el trimestre.
- Si dicho mes tuvo 0 mm caídos indicar con un mensaje.

```python
print("Análisis de lluvias en un trimestre\\n")

mes1 = float(input("Ingrese los mm de lluvia caídos en el primer mes del trimestre: "))
mes2 = float(input("Ingrese los mm de lluvia caídos en el segundo mes del trimestre: "))
mes3 = float(input("Ingrese los mm de lluvia caídos en el tercer mes del trimestre: "))

promedio = (mes1 + mes2 + mes3) / 3

print("Promedio de lluvias caídas:", promedio)

mayores_promedio = 0
if mes1 >= promedio:
    mayores_promedio += 1
if mes2 >= promedio:
    mayores_promedio += 1
if mes3 >= promedio:
    mayores_promedio += 1

print("Cantidad de meses con lluvias mayores al promedio:", mayores_promedio)

if mes1<mes2 and mes1<mes3:
    mes = 1
    men = mes1
else:
    if mes2 < mes3:
        mes = 2
        men = mes2
    else:
        mes = 3
        men = mes3

print("Mes con menos lluvias:", mes)

sin_lluvia = False
if men == 0:
    sin_lluvia = True

if sin_lluvia:
    print("Dicho mes no tuvo lluvias")
```

### **19. Premio por Ventas (*)**

Para calcular el premio de un vendedor, se ingresan 3 montos correspondientes a sus ventas mensuales del último trimestre.

El premio es equivalente al 50% del menor monto vendido. Si además todos los montos superan los $1000, se agrega un 10% adicional al premio calculado.

*(*) Ejercicio tipo parcial*

```python
print('PREMIO POR VENTAS DEL TRIMESTRE')

#Ingreso de datos
monto1 = int(input('Ingrese monto mes 1: '))
monto2 = int(input('Ingrese monto mes 2: '))
monto3 = int(input('Ingrese monto mes 3: '))

#Buscar menor monto
if monto1 < monto2 and monto1 < monto3:
    menor = monto1
elif monto2 < monto3:
    menor = monto2
else:
    menor = monto3

#Calcular premio
premio = menor * 50 / 100

#Calcular adicional
if monto1 > 1000 and monto2 > 1000 and monto3 > 1000:
    adicional = premio * 10 / 100
else:
    adicional = 0
premio += adicional

#Resultados
print('\\nEl premio es de $', premio)
if adicional > 0:
    print('(Incluye adicional de $',adicional,'por ventas altas)')
```

```python
# Solución con bandera
print('PREMIO POR VENTAS DEL TRIMESTRE')

# Ingreso de datos
monto1 = int(input('Ingrese monto mes 1: '))
monto2 = int(input('Ingrese monto mes 2: '))
monto3 = int(input('Ingrese monto mes 3: '))

# Buscar menor monto
if monto1 < monto2 and monto1 < monto3:
    menor = monto1
elif monto2 < monto3:
    menor = monto2
else:
    menor = monto3

# Calcular premio
premio = menor * 50 / 100

# Calcular adicional
recibe_adicional = False
if monto1 > 1000 and monto2 > 1000 and monto3 > 1000:
    adicional = premio * 10 / 100
    premio += adicional
    recibe_adicional = True

# Resultados
print('\\nEl premio es de $', premio)
if recibe_adicional == True:
    print('(Incluye adicional de $', adicional, 'por ventas altas)')
else:
    print('(No corresponde adicional)')
```

### **20. Análisis Estadístico**

Para un análisis estadístico, se pide ingresar 3 valores y determinar:

- Si alguno de los valores es múltiplo de 5
- Si todos ellos son impares
- Si el mayor de ellos supera a la suma de los otros 2

```python
print("Análisis Estadístico")

num1 = int(input("Ingrese el primer valor: "))
num2 = int(input("Ingrese el segundo valor: "))
num3 = int(input("Ingrese el tercer valor: "))

multiplo_5 = False
if num1 % 5 == 0 or num2 % 5 == 0 or num3 % 5 == 0:
    multiplo_5 = True

todos_impares = False
if num1 % 2 == 1 and num2 % 2 == 1 and num3 % 2 == 1:
    todos_impares = True

if num1 > num2 and num1 > num3:
    may = num1
    #otro1 = num2
    #otro2 = num3
    suma = num2 + num3
else:
    if num2 > num3:
        may = num2
        #otro1 = num1
        #otro2 = num3
        suma = num1 + num3
    else:
        may = num3
        #otro1 = num1
        #otro2 = num2
        suma = num1 + num2

supera_suma = False
#suma = otro1 + otro2
if may > suma:
    supera_suma = True

if multiplo_5:
    print("Al menos uno de los valores es múltiplo de 5")
else:
    print("Ningún valor es múltiplo de 5")

if todos_impares:
    print("Todos los valores son impares")
else:
    print("No todos los valores son impares")

if supera_suma:
    print("El mayor de los valores supera la suma de los otros dos")
else:
    print("El mayor de los valores no supera la suma de los otros dos")
```

### **21. Análisis Estadístico (*) - Variante**

Para un análisis estadístico, se pide ingresar 3 valores y determinar:

- Si alguno de los valores es múltiplo de 5
- Cuántos de los valores son impares
- Si el mayor de ellos supera a la suma de los otros 2

*(*) Ejercicio tipo parcial*

```python
print('ANALISIS ESTADISTICO')

# Ingreso de datos
val1 = int(input('Ingrese 1er valor: '))
val2 = int(input('Ingrese 2do valor: '))
val3 = int(input('Ingrese 3er Valor: '))

# Alguno es multiplo de 5?
algun_multiplos_5 = 'NO'
if val1 % 5 == 0 or val2 % 5 == 0 or val3 % 5 == 0:
    algun_multiplos_5 = 'SI'

# Contar impares
cant_impares = 0
if val1 % 2 != 0:
    cant_impares += 1
if val2 % 2 != 0:
    cant_impares += 1
if val3 % 2 != 0:
    cant_impares += 1

# El mayor supera a la suma de los otros dos?
if val1 > val2 and val1 > val3:
    may = val1
    suma = val2 + val3
elif val2 > val3:
    may = val2
    suma = val1 + val3
else:
    may = val3
    suma = val1 + val2

if may > suma:
    mensaje_may = 'Supera'
else:
    mensaje_may = 'No supera'
mensaje_may = mensaje_may + ' a la suma de los otros dos.'

# Resultados
print('-' * 50)
print(algun_multiplos_5, 'hay algun multiplo de 5')
print('Hay', cant_impares, 'valores impares')
print('El valor mayor es', may, '.', mensaje_may)
```

### **22. Votación en el Senado (*)**

Se vota una ley en el Senado, y se ingresan votos a favor, en contra y abstenciones de los senadores presentes.

Informar cuál fue el resultado de la votación. Si la ley fue aprobada, indicar si fue por mayoría absoluta (más del 50% de los votos) o por mayoría simple.

Por último, considerando que la Cámara está formada por 72 senadores, determinar cuantos se encontraban ausentes.

Ejercicio tipo parcial*

```python
print('VOTACION EN EL SENADO')

# Ingresar votos
favor = int(input('Ingrese votos a favor: '))
contra = int(input('Ingrese votos en contra: '))
abstenciones = int(input('Ingrese abstenciones: '))

# Calcultar total
total = favor + contra + abstenciones

# Definir resultado
if favor > contra and favor > abstenciones:
    resultado = 'La ley fue aprobada'
    porcentaje = favor * 100 / total
    if porcentaje > 50:
        resultado += ' por mayoria absoluta'
    else:
        resultado += ' por mayoria simple'
elif contra > abstenciones:
    resultado = 'La ley fue rechazada'
else:
    resultado = 'La ley deberá volver a tratarse'

# Calcular ausentes
ausentes = 72 - total

print('-' * 60)
print(resultado)
if ausentes >= 0:
    print('Hubo', ausentes, 'senadores ausentes')
else:
    print('HUBO FRAUDE!')
```

## Ficha 06: Estructuras repetitivas - Ciclo while

### **1. Complejo de cines**

Desarrollar un programa que permita procesar funciones de un complejo de cines. Por cada función se conoce: cantidad de espectadores y descuento (S/N). La carga termina cuando la cantidad de espectadores sea igual a 0 (cero).

El programa deberá:

a) Calcular la recaudación total del complejo, considerando que el valor de la entrada es de $50 en los días con descuento y $75 en los días sin descuento.

b) Determinar cuántas funciones con descuento se efectuaron y qué porcentaje representan sobre el total de funciones.

```python
print('COMPLEJO DE CINES')
print('*' * 80)

# Inicializar contadores y acumuladores
monto = 0
funciones = 0
funciones_dto = 0

# Primera carga de datos de corte antes del ciclo
espectadores = int(input('Espectadores (con 0 termina): '))

# Proceso repetitivo
while espectadores != 0:
    # Carga de datos que no determinan el corte del ciclo
    descuento = input('Descuento (S/N): ')
    # Definir precio
    if descuento == 'S':
        precio = 50
    else:
        precio = 75
    # Acumular monto recaudado por función
    monto = monto + (espectadores * precio)
    # Contar funciones con descuento y total de funciones
    if descuento == 'S':
        funciones_dto += 1
    funciones += 1
    # Nueva carga de datos de corte dentro del ciclo
    espectadores = int(input('Espectadores (con 0 termina): '))

# Resultados
print('*'*80)
print('Recaudación total $',monto)
if funciones != 0:
    porc = funciones_dto * 100 / funciones
else:
    porc = 0
print('Porcentaje de funciones con descuento:', porc,'%')
```

### **2. Ventas por sucursal**

Ingresar una serie de números por teclado que representan la cantidad de ventas realizadas en las diferentes sucursales de un país de una determinada empresa.

Los requerimientos funcionales del programa son:

a) Informar la cantidad de ventas ingresadas.

b) Total de ventas.

c) Cantidad de ventas cuyo valor este comprendido entre 100 y 300 unidades.

d) Cantidad de ventas con 400, 500 y 600 unidades.

e) Indicar si hubo una cantidad de ventas inferior a 50 unidades.

Usted deberá ingresar cantidades de ventas hasta que se ingrese un valor negativo.

```python
cant_venta = 0
tot_venta = 0
cant_venta1 = 0
cont_venta400 = 0
cont_venta500 = 0
cont_venta600 = 0
hay_menor_50 = False

venta = int(input('Ingrese una cantidad de ventas (negativo para terminar): '))
while venta >= 0:
    # Permite ir contabilizando la cantidad de ventas
    cant_venta += 1
    # Permite acumular el total de ventas.
    tot_venta += venta

    # Permite contabilizar la cantidad de ventas entre 200 y 300 unidades.
    if (venta >= 100 and venta <= 300):
        cant_venta1 += 1
    # Permite contabilizar la cantidad de ventas con 400, 500 y 600 unidades.
    if venta == 400:
        cont_venta400 += 1
    if venta == 500:
        cont_venta500 += 1
    if venta == 600:
        cont_venta600 += 1

    #Determina si hubo una venta inferior a 50 unidades.
    if venta < 50:
        hay_menor_50 = True

    venta = int(input('Ingrese otra cantidad de ventas (0 cero para terminar): '))

print('La cantidad de ventas ingresadas fueron: ', cant_venta)
print('El total de ventas ingresadas fue:', tot_venta)
print('La cantidad de ventas comprendidas entre 200 y 300 unidades es:', cant_venta1)
print('La cantidad de ventas con 400 unidades es:', cont_venta400)
print('La cantidad de ventas con 500 unidades es:', cont_venta500)
print('La cantidad de ventas con 600 unidades es:', cont_venta600)

if hay_menor_50 == True:
    print ('Hubo al menos alguna venta con menos de 50 unidades')
else:
    print('No hubo venta con menos de 50 unidades')
```

### **3. Menú y números aleatorios**

Realice un programa que le ofrezca al usuario un menú de opciones que le permita ejecutar las siguientes acciones:

Opción 1: Calcular promedio de 1.000 números aleatorios generados en el rango de [0, 100.000].

Opción 2: Buscar el mayor de 10.000 números aleatorios generados en el rango de [0, 100.000].

Opción 3: Buscar el menor de 5.000 números aleatorios generados en el rango de [0, 100.000] y calcular el valor promedio de los números menores a 10.000.

Cualquier otro número: Salir del programa.

```python
import random

print("Seleccione la opción del menú que prefiera:")
print("1- Calcular promedio de 1.000 números aleatorios.")
print("2- Buscar el mayor de 10.000 números aleatorios.")
print("3- Buscar el menor de 100.000 números aleatorios.")
print("Cualquier numero- Salir.")
op=int(input("Opción:"))

while op > 0 and op < 4:
    if op == 1:
        acumulador = 0
        i = 0
        while i < 1000:
            n = random.randint(0, 100000)
            acumulador += n
            i += 1
        promedio = acumulador / i
        print("El promedio es", promedio)
    elif op == 2:
        mayor = 0
        i = 0
        while i < 10000:
            n = random.randint(0, 100000)
            if mayor < n:
                mayor = n
            i += 1
        print("El mayor es", mayor)
    else:
        menor = 100000
        i = 0
        suma = 0
        cont = 0
        while i < 5000:
            n = random.randint(0, 100000)
            if menor > n:
                menor = n
            if n < 10000:
                suma += n
                cont += 1
            i += 1
        if cont != 0:
            p = suma / cont
        else:
            p = 0
        print("El menor es", menor, "y el promedio de los menores a 10000 es:", p)

    print("Seleccione la opción del menú que prefiera:")
    print("1- Calcular promedio de 1.000 números aleatorios.")
    print("2- Buscar el mayor de 10.000 números aleatorios.")
    print("3- Buscar el menor de 100.000 números aleatorios.")
    print("Cualquier numero- Salir.")
    op = int(input("Opción:"))

print("Fin del programa :)")
```

### **4. Promedio de números aleatorios**

Realice un programa que permita calcular el promedio de 1000 números aleatorios generados en el rango de [0, 100000]

```python
import random

print('Calcular promedio de aleatorios')
print('=' * 80)

acumulador = 0
i = 0
while i < 1000:
    n = random.randint(0, 100000)
    acumulador += n
    i += 1
promedio = acumulador / i
print("El promedio es", promedio)

print("Fin del programa :)")
```

### **5. Búsqueda de mayor**

Realizar un programa que permita buscar el mayor de 10.000 números aleatorios generados en el rango de [0, 100.000].

```python
import random

print('Buscar el mayor de los valores')
print('=' * 80)

mayor = 0
i = 0
while i < 10000:
    n = random.randint(0, 100000)
    if mayor < n:
        mayor = n
    i += 1

print('El mayor valor de los 10000 numeros aleatorios es:', mayor)
print("Fin del programa :)")
```

### **6. Menores y promedio**

Realizar un programa que genere 5000 numeros aleatorios en el rango de [0, 100000] y que permita:

- Determinar el menor de los numeros generados en forma aleatoria
- Calcular el valor promedio de los números menores a 10.000.

```python
import random

menor = None
i = 0
suma = 0
cont = 0
while i < 5000:
    n = random.randint(0, 100000)
    if menor is None or menor > n:
        menor = n
    if n < 10000:
        suma += n
        cont += 1
    i += 1
if cont != 0:
    p = suma / cont
else:
    p = 0
print("El menor es", menor, "y el promedio de los menores a 10000 es:", p)
```

### **7. Números pares e impares**

Se pide desarrollar un programa que permita leer una serie de números. La finalización de carga de datos se presenta cuando el usuario ingrese un número negativo.

Los requerimientos funcionales del programa son:

a) La sumatoria de solo los números que estén comprendidos entre 50 y 100.

b) Cantidad de valores pares ingresados.

c) Cantidad de valores impares ingresados.

d) Informar si en la carga de números se ingreso al menos un número 0.

e) Informar si la serie contiene solo números pares e impares alternados

```python
print('Procesamiento de Numeros Pares e Impares')

sumatoria = 0
cantidad_pares = 0
cantidad_impares = 0
ingreso_cero = False
anterior = -1
alternan = True

numero = int(input('Ingrese un numero (finaliza cuando ingrese un numero negativo): '))
while numero >= 0:
    if 50 < numero < 100:
        sumatoria += numero

    paridad = numero % 2
    if paridad == 0:
        cantidad_pares += 1
    else:
        cantidad_impares += 1

    if numero == 0:
        ingreso_cero = True

    if anterior == paridad:
        alternan = False
    anterior = paridad
    numero = int(input('Ingrese otro numero a procesar: '))

print('Resultados')
print('=' * 80)
print('La sumatoria de los numeros comprendidos entre 50 y 100 fue de', sumatoria)
print('La cantidad de numeros pares procesados fue de', cantidad_pares)
print('La cantidad de numeros impares procesados fue de', cantidad_impares)
if ingreso_cero:
    print('El usuario al menos ingreso un numero cero en la secuencia')

if alternan:
    print('La secuencia tiene numeros pares e impares alternados')
else:
    print('La secuencia no tiene numeros pares e impares alternados')
```

### **8. Censo**

Desarrollar un programa que permita procesar los datos del último censo de una pequeña población.

Por cada habitante se ingresa: sexo (M/F) y edad. La carga de datos finaliza al ingresar cualquier otro valor para sexo.

El programa debe informar:

a) A qué sexo corresponde la mayor cantidad de habitantes (considerar que puede ser igual)

b) Cantidad de mujeres en edad escolar (4 a 18 años inclusive)

c) Si hay algún varón que supere los 80 años de edad

```python
print('CENSO POBLACIONAL')
print('*' * 80)

# Inicializar contadores y acumuladores
cant_hombres = 0
cant_mujeres = 0
cant_escolares = 0
hay_mayores80 = False

# Primera carga de datos de corte antes del ciclo
sexo = input('Ingrese sexo (M/F - Otro valor termina): ')

# Proceso repetitivo
while sexo == 'M' or sexo == 'F':
    # Carga de datos que no determinan el corte del ciclo
    edad = int(input('Ingrese edad: '))
    # Contar hombres y mujeres
    if sexo == 'M':
        cant_hombres += 1
    else:
        cant_mujeres += 1
    # Contar mujeres en edad escolar
    if sexo == 'F' and edad >= 4 and edad <= 18:
        cant_escolares += 1
    # Detectar hombres de más de 80 años
    if sexo == 'M' and edad > 80:
        hay_mayores80 = True
    # Nueva carga de dato de corte dentro del ciclo
    sexo = input('Ingrese sexo (M/F - Otro valor termina): ')

# Resultados
print('*' * 80)
if cant_hombres > cant_mujeres:
    print('Hay más hombres que mujeres')
elif cant_mujeres > cant_hombres:
    print('Hay más mujeres que hombres')
else:
    print('La cantidad de mujeres y hombres es igual')
print('Las mujeres en edad escolar son:', cant_escolares)
if hay_mayores80 == True:
    print('Hay hombres mayores a 80 años')
else:
    print('NO hay hombres mayores a 80 años')
```

```python
# Solución con condicionales anidadas
print('CENSO POBLACIONAL')
print('*' * 80)

# Inicializar contadores y acumuladores
cant_hombres = 0
cant_mujeres = 0
cant_escolares = 0
hay_mayores80 = False

# Primera carga de datos de corte antes del ciclo
sexo = input('Ingrese sexo (M/F - Otro valor termina): ')

# Proceso repetitivo
while sexo == 'M' or sexo == 'F':
    # Carga de datos que no determinan el corte del ciclo
    edad = int(input('Ingrese edad: '))
    # Proceso
    if sexo == 'M':
        cant_hombres += 1
        if edad > 80:
            hay_mayores80 = True
    else:
        cant_mujeres += 1
        if edad >= 4 and edad <= 18:
            cant_escolares += 1
    # Nueva carga de dato de corte dentro del ciclo
    sexo = input('Ingrese sexo (M/F - Otro valor termina): ')

# Resultados
print('*' * 80)
if cant_hombres > cant_mujeres:
    print('Hay más hombres que mujeres')
elif cant_mujeres > cant_hombres:
    print('Hay más mujeres que hombres')
else:
    print('La cantidad de mujeres y hombres es igual')
print('Las mujeres en edad escolar son:', cant_escolares)
if hay_mayores80 == True:
    print('Hay hombres mayores a 80 años')
else:
    print('NO hay hombres mayores a 80 años')
```

### **9. Mayor numero en orden par**

Ingresar de a uno una serie de números. Encontrar e imprimir el mayor de todos los números pares cuyo número de orden sea par, el proceso terminará cuando el número leído sea igual a cero

```python
print('Busqueda del mayor par de orden par')
print('=' * 80)

orden = 0
mayor = None

numero = int(input('Ingrese un numero (finaliza cuando ingrese 0): '))

while numero != 0:
    # Si es número par en orden par,
    if orden % 2 == 0 and numero % 2 == 0:
        # se busca el mayor
        if mayor is None or numero > mayor:
            mayor = numero
    orden += 1
    numero = int(input('Ingrese otro numero: '))

if not mayor is None:
    print('El mayor numero par ingresado en orden par es', mayor)
else:
    print('No se ingresaron números pares en orden par')
```

### **10. Comisión de Vendedores**

Una empresa debe calcular el total de comisiones que debe abonar por ventas realizadas por sus vendedores, para ello le solicita un sistemita que le permita calcular dicho montos.

Se tiene conocimiento que la empresa tiene cuatro categorías de vendedores (1 a 4). Usted debe solicitar el ingreso de la categoría del vendedor y el total de la venta (el proceso termina cuando se ingrese una categoría igual a cero) y acumular las comisiones de las ventas rendidas por los vendedores de diferentes en base a los siguientes cálculos:

a) Categoría 1: cobra una comisión de 10%b) Categoría 2: cobra una comisión de 25%c) Categoría 3: cobra una comisión de 30%d) Categoría 4: cobra una comisión de 40%

Una vez procesadas todas las ventas mostrar el total de comisiones a pagar por cada categoría de vendedores que tiene la empresa junto con el total general

```python
print('Sistema de Calculo de Comisiones a Vendedores')
print('*' * 80)

tot_cat_1 = 0
tot_cat_2 = 0
tot_cat_3 = 0
tot_cat_4 = 0

print('Inicio de calculo de comision, al entrar una categoria igual a 0 el proceso termina')
categoria = int(input('Ingrese la categoria de vendedor (1-4): '))

while categoria != 0:
    venta = float(input('Ingrese el total vendido por este vendedor: '))

    if categoria == 1:
        tot_cat_1 += venta * 0.10
    elif categoria == 2:
        tot_cat_2 += venta * 0.25
    elif categoria == 3:
        tot_cat_3 += venta * 0.30
    else:
        tot_cat_4 += venta * 0.40

    categoria = int(input('Ingrese una nueva categoria de vendedor (1-4): '))

total = tot_cat_1 + tot_cat_2 + tot_cat_3 + tot_cat_4

print('Resultados de comisiones calculadas')
print('*' * 80)
print('El total de comisiones a pagar para la categoria 1 es de $', tot_cat_1, sep='')
print('El total de comisiones a pagar para la categoria 2 es de $', tot_cat_2, sep='')
print('El total de comisiones a pagar para la categoria 3 es de $', tot_cat_3, sep='')
print('El total de comisiones a pagar para la categoria 4 es de $', tot_cat_4, sep='')
print('El total de comisiones a pagar es de $', total, sep='')
```

### **11. Proceso de Discriminantes**

Un matemático desea un simple programa que le permita cargar una serie de números que representan los discriminantes de diferentes ecuaciones de segundo grado, el proceso de la secuencia finaliza cuando el matemático no desea seguir cargando discriminantes. Usted debe:

a) Determinar la cantidad de discriminantes que darán 2 raícesb) Determinar la cantidad de discriminantes que darán una única raízc) Determinar la cantidad de discriminantes que daran raíces en el campo de los números imaginariosd) Indicar el porcentaje que representa el punto c sobre el total de discriminantes procesados por el matemático

```python
print('Proceso de discriminantes de polinomios de segundo grado')
print('=' * 75)

cant_2raices = 0
cant_1raiz = 0
cant_raices_complejas = 0

sigue = input('Dese procesar un discriminante (S/N): ')
while sigue == 'S':
    delta = int(input('Ingrese el discriminante a procesar: '))
    if delta > 0:
        cant_2raices += 1
    elif delta == 0:
        cant_1raiz += 1
    else:
        cant_raices_complejas += 1

    sigue = input('Desea continuar procesando otro discriminante (S/N): ')

total = cant_2raices + cant_1raiz + cant_raices_complejas

print('La cantidad de discriminantes con que se obtendran 2 raices son:', cant_2raices)
print('La cantidad de discriminantes con que se obtendra 1 raiz son:', cant_1raiz)
print('La cantidad de discriminantes con que se obtendran raices imaginarias son:', cant_raices_complejas)
if total > 0:
     porc = cant_raices_complejas * 100 / total
     print('El porcentaje de discriminantes que obtienen raices complejas es: ', round(porc,2), '%', sep='')
```

## Ficha 07: Estructuras repetitivas: Ciclo for

### **1. Ciclistas**

La final de una carrera de ciclistas tiene *n* competidores (n se ingresa por teclado).

Desarrollar un programa que permita cargar, por cada competidor, nombre y tiempo de carrera. Luego se pide:

a) Determinar y mostrar el nombre del ganador de la carrera.

b) Ingresar por teclado el tiempo record registrado para dicha carrera. Determinar si el tiempo del ganador es menor al tiempo record, mostrar un mensaje.

c) Calcular y mostrar el tiempo promedio entre todos los ciclistas.

```python
suma_tiempos = 0
menor_tiempo = None
menor_nombre = None

es_el_primero = True

n = int(input("Ingrese la cantidad de corredores"))

for i in range(n): # La variable i toma los valores entre 0 y n-1
    # Este ciclo va a dar una vuelta por cada ciclista

    nombre = input("Ingrese el nombre del ciclista: ")
    tiempo = int(input("Ingrese el tiempo: "))

    # Búsqueda del menor tiempo
    # Tenemos que garantizar que menor_tiempo empiece igual al primer valor

    # Alternativas válidas
    # if i == 0 or tiempo < menor_tiempo:
    # if es_el_primero or tiempo < menor_tiempo:
    # if menor is None or tiempo < menor_tiempo:
    if es_el_primero or tiempo < menor_tiempo:
        menor_tiempo = tiempo
        menor_nombre = nombre

    # Promedio: acumulador / contador
    suma_tiempos += tiempo
    es_el_primero = False

promedio_tiempos = suma_tiempos / n

# Esta variable podria ser ingresada al principio
tiempo_record = int(input("Ingrese el tiempo record"))

if menor_tiempo < tiempo_record:
    print("El ganador batió el record!!!!")

print("El nombre del ciclista que hizo el menor tiempo es: ", menor_nombre)
print("El promedio de tiempos es:", promedio_tiempos)
suma_tiempos = 0
menor_tiempo = None
menor_nombre = None

es_el_primero = True

n = int(input("Ingrese la cantidad de corredores"))

for i in range(n): # La variable i toma los valores entre 0 y n-1
    # Este ciclo va a dar una vuelta por cada ciclista

    nombre = input("Ingrese el nombre del ciclista: ")
    tiempo = int(input("Ingrese el tiempo: "))

    # Búsqueda del menor tiempo
    # Tenemos que garantizar que menor_tiempo empiece igual al primer valor

    # Alternativas válidas
    # if i == 0 or tiempo < menor_tiempo:
    # if es_el_primero or tiempo < menor_tiempo:
    # if menor is None or tiempo < menor_tiempo:
    if es_el_primero or tiempo < menor_tiempo:
        menor_tiempo = tiempo
        menor_nombre = nombre

    # Promedio: acumulador / contador
    suma_tiempos += tiempo
    es_el_primero = False

promedio_tiempos = suma_tiempos / n

# Esta variable podria ser ingresada al principio
tiempo_record = int(input("Ingrese el tiempo record"))

if menor_tiempo < tiempo_record:
    print("El ganador batió el record!!!!")

print("El nombre del ciclista que hizo el menor tiempo es: ", menor_nombre)
print("El promedio de tiempos es:", promedio_tiempos)
suma_tiempos = 0
menor_tiempo = None
menor_nombre = None

es_el_primero = True

n = int(input("Ingrese la cantidad de corredores"))

for i in range(n): # La variable i toma los valores entre 0 y n-1
    # Este ciclo va a dar una vuelta por cada ciclista

    nombre = input("Ingrese el nombre del ciclista: ")
    tiempo = int(input("Ingrese el tiempo: "))

    # Búsqueda del menor tiempo
    # Tenemos que garantizar que menor_tiempo empiece igual al primer valor

    # Alternativas válidas
    # if i == 0 or tiempo < menor_tiempo:
    # if es_el_primero or tiempo < menor_tiempo:
    # if menor is None or tiempo < menor_tiempo:
    if es_el_primero or tiempo < menor_tiempo:
        menor_tiempo = tiempo
        menor_nombre = nombre

    # Promedio: acumulador / contador
    suma_tiempos += tiempo
    es_el_primero = False

promedio_tiempos = suma_tiempos / n

# Esta variable podria ser ingresada al principio
tiempo_record = int(input("Ingrese el tiempo record"))

if menor_tiempo < tiempo_record:
    print("El ganador batió el record!!!!")

print("El nombre del ciclista que hizo el menor tiempo es: ", menor_nombre)
print("El promedio de tiempos es:", promedio_tiempos)
```

```python
print('CARRERA DE CICLISTAS')
print('-' * 40)
cont = acum = 0
ganador = None

n = int(input('Ingrese la cantidad de ciclistas que participan de la carrera: '))

for i in range(n):
    print('Ciclista',i)
    nombre = input('Ingrese nombre: ')
    tiempo = int(input('Ingrese tiempo: '))
    if ganador is None or tiempo < ganador[1]:
        ganador = nombre, tiempo
    cont += 1
    acum += tiempo

print('-' * 40)
if n > 0:
    record = int(input('Ingrese record actual: '))
    print('El ganador es', ganador[0])
    if ganador[1] < record:
        print('El ganador supero el record!')
        if cont > 0:
            promedio = round(acum / cont,2)
        else:
            promedio = 0
        print('Tiempo promedio general', promedio)
else:
    print('No se ingresaron datos')
```

### **2. Secuencia de impares**

Cargar por teclado dos números, e imprimir los números impares que se encuentran comprendidos entre ellos, en forma ascendente y descendente.

```python
print('SECUENCIA DE IMPARES')
print('=' * 40)

num1 = int(input('Ingrese un número: '))
num2 = int(input('Ingrese otro: '))

#Identificamos menor y mayor para saber como ordenar la secuencia
if num1 < num2:
    men, may = num1, num2
else:
    men, may = num2, num1

#Ajustamos valores si son pares
if men % 2 == 0:
    men += 1
if may % 2 == 0:
    may -= 1

#Resultados
print('Secuencia ascendente:')
ascend = range(men, may + 1, 2)
for num in ascend:
    print(num, end=' | ')

print('\\nSecuencia descendente:')
descend = range(may, men -1, -2)
for num in descend:
    print(num, end=' | ')
```

```python
# Solución 2
print('SECUENCIA DE IMPARES')
print('=' * 40)

num1 = int(input('Ingrese un número: '))
num2 = int(input('Ingrese otro: '))

#Definimos límites de la secuencia ascendente
if num1 < num2:
    inicio, fin = num1, num2 + 1
else:
    inicio, fin = num2, num1 + 1

#Corregimos inicio si es par
if inicio % 2 == 0:
    inicio += 1

#Mostramos secuencia
print('Secuencia ascendente')
for num in range(inicio, fin, 2):
    print(num, end=' ')

#Definimos límites de la secuencia descendente
if num1 > num2:
    inicio, fin = num1, num2 - 1
else:
    inicio, fin = num2, num1 - 1

#Corregimos inicio si es par
if inicio % 2 == 0:
    inicio += 1

#Mostramos secuencia
print('\\nSecuencia descendente')
for num in range(inicio, fin, -2):
    print(num, end=' ')
```

### **3. Sueldos y aguinaldo**

Ingresar por teclado los sueldos de un vendedor, correspondientes al primer semestre del año y luego:

a) Calcular su aguinaldo, sabiendo que es la mitad del sueldo más alto del período.

b) Determinar en qué mes recibió el sueldo más bajo del período.

c) Informar el sueldo promedio del semestre.

```python
# Solución con secuencia
print('SUELDOS Y AGUINALDO')
print('*' * 80)

#Datos y proceso
total = 0
primero = True
semestre = ("Enero","Febrero","Marzo","Abril","Mayo","Junio")
for mes in semestre:
    sueldo = float(input("Ingrese sueldo de " + str(mes) + ": "))
    if primero==True:
        may = sueldo
        men = sueldo, mes
        primero = False
    else:
        if sueldo > may:
            may = sueldo
        if sueldo < men[0]:
            men = sueldo, mes
    total += sueldo

#Resultados
aguinaldo = may / 2
print ("\\nEl aguinaldo es de $",aguinaldo)
print("El menor sueldo fue de $",men[0],"y lo obtuvo en el mes de",men[1])
promedio = round(total/len(semestre),2)
print ("El sueldo promedio es de $",promedio)
```

```python
# Solución con range
print('SUELDOS Y AGUINALDO')
print('*' * 80)

#Datos y proceso
total = 0
for mes in range(1,7):
    sueldo = float(input("Ingrese sueldo mes " + str(mes) + ": "))
    if mes==1:
        may = sueldo
        men = sueldo,1
    else:
        if sueldo > may:
            may = sueldo
        if sueldo < men[0]:
            men = sueldo, mes
    total += sueldo

#Resultados
aguinaldo = may / 2
print ("\\nEl aguinaldo es de $",aguinaldo)
print("El menor sueldo fue de $",men[0],"y lo obtuvo en el mes",men[1])
promedio = round(total/6,2)
print ("El sueldo promedio es de $",promedio)
```

### **4. Decimal a Hexadecimal**

Generar n numeros aleatorios entre el rango de 5000 y 450000, por cada uno de ellos mostrar y generar el numero hexadecimal

```python
import random
n = int(input('Ingrese la cantidad de numeros a procesar: '))

for i in range(n):
    numero = random.randrange(5000, 450000)
    hexadecimal = ''
    #proceso de conversion hexadecimal
    valor = numero % 16
    siguiente = numero // 16
    digito = ''
    while valor > 0:
        if valor < 10:
            digito = str(valor)
        else:
            digito = chr(55 + valor)
        hexadecimal = digito + hexadecimal
        valor = siguiente % 16
        siguiente //= 16

    print('El numero ', numero, 'en hexadecimal es', hexadecimal)
```

### **5. Números Enteros**

Escribir un programa que permita leer la cantidad de números enteros ingresados por el usuario y calcular lo siguiente:

a) El segundo menor

b) El promedio de los números positivos.

c) El mayor de los números negativos.

```python
n=int(input("Ingrese la cantidad de nros. a procesar: "))
contador_positivos=0
suma_positivos=0
mayor_negativos=0

for i in range(n):

    #Entrada
    print("Ingrese el número ", i+1)
    numero=int(input())

    #Subproblema 1: Búsqueda del segundo menor
    if i==0:
        menor=numero
    elif i==1:
        if numero<menor:
            segundoMenor=menor
            menor=numero
        else:
            segundoMenor=numero
    else:
        if numero<menor:
            segundoMenor=menor
            menor=numero
        elif numero<segundoMenor:
            segundoMenor=numero

    #Subproblema 2: El promedio de los numeros positivos
    if numero>=0:
        contador_positivos+=1
        suma_positivos+=numero

    #Subproblema 3: El mayor de los numeros negativos.
    else:
        if mayor_negativos==0:
            mayor_negativos=numero
        elif mayor_negativos<numero:
            mayor_negativos=numero

if contador_positivos!=0:
    promedio=suma_positivos/contador_positivos
else:
    promedio=0

#Salida
print("El segundo menor es:",segundoMenor)
print ("El promedio de numeros positivos es: ",promedio)
print ("El mayor de los numeros negativos es: ",mayor_negativos)
```

### **6. Puntos en un plano**

Desarrollar un programa que permita ingresar las coordenadas de *n* puntos en el plano, e informe:

a) En qué cuadrante se encuentra cada uno.

b) Determinar cuántos puntos se encuentran en el primer o tercer cuadrante.

c) Determinar cuál de todos los puntos cargados se encuentra a mayor distancia del origen de coordenadas.

```python
print('Procesamiento de puntos en el plano')
print('_' * 80)
n = int(input('Ingrese la cantidad de puntos a procesar: '))

cant_primer_cuadrante = 0
cant_tercer_cuadrante = 0
mayor_distancia = 0
mayor_punto = ()

for vuelta in range(n):
    eje_x = float(input('Ingrese el valor de la abscisa del punto: '))
    eje_y = float(input('Ingrese el valor de la ordenada del punto: '))

    if eje_x > 0:
        if eje_y > 0:
            cuadrante = "primer"
            cant_primer_cuadrante += 1
        else:
            cuadrante = "cuarto"
    else:
        if eje_y > 0:
            cuadrante = "segundo"
        else:
            cuadrante = "tercer"
            cant_tercer_cuadrante += 1

    print('El punto (', eje_x, ',', eje_y, ') ',
          'se encuentra en el ', cuadrante ,' cuadrante', sep='')

    distancia_origen = math.sqrt(pow(eje_x, 2) + pow(eje_y, 2))
    if distancia_origen > mayor_distancia:
        mayor_distancia = distancia_origen
        mayor_punto = eje_x, eje_y

    print('-' * 80)

print('_' * 80)
print('La cantidad de puntos en el primer cuadrante fue de: ',
      cant_primer_cuadrante)
print('La cantidad de puntos en el tercer cuadrante fue de: ',
      cant_tercer_cuadrante)
print('El punto con mayor distancia al origen fue (',
      mayor_punto[0], ',', mayor_punto[1], ")", sep='')
```

### **7. Números: Mayor y Menor**

Cargar por teclado n números enteros positivos, uno a uno. Se deberá establecer qué número es el mayor de los números pares y el menor de los números impares.

Por ejemplo, en una secuencia de números: 8, 15, 9, 2, 27, 18, 0; el mayor de los pares sería el número 18 y el menor de los impares el número 9.

```python
print('Busqueda de Mayores Pares y Menores Impares')
print('-' * 80)

print('Se procesarán enteros positivos, con el cero se termina la carga: ')
numero = int(input('Ingrese un numero entero positivo: '))

mayor_par = 0
menor_impar = 0
primer_impar = True

while numero > 0:
    paridad = numero % 2
    if paridad == 0:
        if numero > mayor_par:
            mayor_par = numero
    else:
        if primer_impar or numero < menor_impar:
            primer_impar = False
            menor_impar = numero

    numero = int(input('Ingrese un nuevo numero entero positivo: '))

if mayor_par != 0:
    print('El mayor numero de los pares es:', mayor_par)
else:
    print('No ingreso numeros pares')

if menor_impar != 0:
    print('El menor numero de los impares es:', menor_impar)
else:
    print('No ingreso numeros impares')
```

### **8. Ejercicio Estadística de Guardería Náutica**

Un club náutico de la costa del lago San Roque necesita calcular estadísticas acerca de los barcos que tiene en la guardería.

Se pretende un programa que cargue uno por uno los datos de cada barco. De ellos se sabe el nombre, el tipo (1 si es velero, 2 si es lancha) y el monto que pagan por mes de guardería.

El programa debe cargar datos de los barcos de acuerdo a una cantidad n que se carga al comienzo y una vez completada la carga informar:

1. El total anual aportado por los veleros y el total anual aportado por las lanchas (2 totales).
2. El nombre del velero que mayor cuota mensual paga de guardería y el valor de su cuota mensual.
3. El valor promedio de cuota pagada por las embarcaciones de la guardería teniendo en cuenta todas las embarcaciones independientemente del tipo que tengan.
4. El porcentaje que representa el monto mensual recaudado por los veleros sobre el total mensual recaudado y el porcentaje que representa el monto mensual recaudado por las lanchas sobre el total mensual recaudado (2 porcentajes).

```python
# Encabezado de la consola
print()
print('_' * 40)
print('Programa de estadísticas del Club Naútico')
print('_' * 40)
print()

# Leer la cantidad de datos a cargar (n que representa la cantidad de barcos)
n = int(input('Ingrese la cantidad de Embarcaciones a cargar: '))

# Segmento de inicialización de contadores acumuladores y banderas
total_anual_veleros = total_anual_lanchas = 0
primero = True
suma_total_mensual = suma_mensual_veleros = suma_mensual_lanchas = 0
cantidad = 0

# Comienza la carga y proceso de los datos
print()
print('Cargue los datos de las Embarcaciones...')
print()
for i in range(n):
    # Lectura de datos de cada barco
    nombre = input('Ingrese el nombre de la Embarcación: ')
    tipo = int(input('Ingrese el tipo de embarcación (1 - para Veleros o 2 - para Lanchas): '))
    importe_mensual = float(input('Ingrese el importe mensual pagado: '))

    if tipo == 1:
        # Incremento el total anual de los veleros
        # Esto también se podría resolver al final a partir del total mensual
        total_anual_veleros += importe_mensual * 12

        # Busco el velero con mayor cuota mensual
        # Utilizamos la alternativa que sirve para todos los casos por más que como dijimos en este caso había otras opciones
        if primero or importe_mensual > mayor_cuota:
            mayor_cuota = importe_mensual
            nombre_mayor = nombre
            primero = False

        # Incremento la suma mensual para los veleros para el cálculo de los porcentajes
        suma_mensual_veleros += importe_mensual
    else:
        # Incremento el total anual de las lanchas
        # También se podría resolver al final a partir del total mensual
        total_anual_lanchas += importe_mensual * 12

        # Incremento la suma mensual para las lanchas para el cálculo de los porcentajes
        suma_mensual_lanchas += importe_mensual

    # Incremento la suma total
    # (como también dijimos en clase este valor también se podía calcular porque en este caso en ambas ramas del if estamos sumando cada importe
    suma_total_mensual += importe_mensual

    # Cuento la cantidad de barcos
    cantidad += 1

# Si se cargaron barcos, Calculo el promedio pedido en el punto 3
if cantidad > 0:
    promedio = suma_total_mensual / cantidad

# Calculo los porcentajes solicitados en el punto 4
porcentaje_veleros = suma_mensual_veleros * 100 / suma_total_mensual
porcentaje_lanchas = suma_mensual_lanchas * 100 / suma_total_mensual

# Muestro los resultados solicitados
print()
print('_' * 40)
print('Resultados estadísticos')
print('_' * 40)
print()

print('El total anual aportado por los Veleros es:', round(total_anual_veleros, 2))
print('El total anual aportado por las Lanchas es:', round(total_anual_lanchas, 2))

# Para el caso del mayor valido que se haya cargado algun velero y sino muestro un mensaje
print()
if not primero:
    print('El Velero que mayor cuota mensual paga es:', nombre_mayor, 'y paga:', mayor_cuota)
else:
    print('No se cargaron Veleros, por lo que no hay Velero con mayor cuota mensual...')

print()
print('La cuota mensual promedio abonada por todas las embarcaciones fue:', round(promedio, 2))

print()
print('De un total mensual recuadudado de:', suma_total_mensual)
print('Los Veleros aportaron un ' + str(round(porcentaje_veleros, 2)) + '%')
print('Las Lanchas aportaron un ' + str(round(porcentaje_lanchas, 2)) + '%')

# Muestro un mensaje de fin y solicito que presione enter para finalizar
print()
print('_' * 40)
print('Fin.')
print('_' * 40)
```

### **9. Validación de cuenta**

Desarrollar un programa que permita validar la cuenta de un usuario que intenta ingresar al sistema.

La cuenta debe ingresarse con formato nombre@dominio y el programa validará que cumpla con las siguientes reglas:

- Tener un solo @ en una posición intermedia de la cadena (ni la primera ni la última letra)
- No contener dos puntos seguidos (uno a continuación del otro)
- No empezar ni terminar con un punto

```python
#Datos
cant_arrobas = 0
pos_arroba = -1
dos_puntos = False
anterior = None
print('INICIO DE SESIÓN')
cuenta = input('Ingrese cuenta: ')

#Proceso
pos = 0
for car in cuenta:
    if car == '@':
        cant_arrobas += 1
        pos_arroba = pos
    elif car == '.' and anterior == '.':
        dos_puntos = True
    pos += 1
    anterior = car

#Resultados
if cant_arrobas != 1 or pos_arroba == 0 or pos_arroba == len(cuenta)-1:
    print('Error! La cantidad y/o ubicacion de @ es incorrecta.')
elif dos_puntos:
    print('Error! La cuenta tiene dos puntos seguidos.')
elif cuenta[0] == '.' or cuenta[-1]=='.':
    print('Error! La cuenta empieza o termina con punto.')
else:
    print('Cuenta válida. Ingreso autorizado')
```

### **10. Dirección de Tránsito**

La Dirección de Tránsito de Córdoba necesita un programa que permita validar las patentes que se ingresan al sistema.

El programa debe solicitar el ingreso de una patente (sin espacios intermedios) y luego:

- Informar si se trata de una patentes en formato antiguo (XXX999) o nuevo (XX999YY)
- Verificar que contenga letras y números de acuerdo a los esperado

```python
# Datos
print('DIRECCIÓN DE TRÁNSITO')
patente = input('Ingrese patente (sin espacios intermedios): ')
print('-' * 80)

# Validar formato
ok = True
if len(patente) == 6:
    print('Formato antiguo')
elif len(patente) == 7:
    print('Formato nuevo')
else:
    print('Formato INVÁLIDO!')
    ok = False

# Validar caracteres
if ok:
    pos = 0
    for car in patente:
        if (car >= 'A' and car <= 'Z') or (car >= 'a' and car <= 'z'):
            if len(patente) == 6 and pos >= 3:
                ok = False
            elif len(patente) == 7 and pos >= 2 and pos <= 4:
                ok = False
        elif car >= '0' and car <= '9':
            if len(patente) == 6 and pos <= 2:
                ok = False
            elif len(patente) == 7 and (pos <= 1 or pos >=5):
                ok = False
        else:
            ok = False
        pos += 1

if ok:
    print('La patente es válida')
else:
    print('La patente NO es válida')
```

## Ficha 08: Estructura repetitivas - Variantes

### **1. Secuencia numérica**

Ingresar una secuencia de números, de a uno por vez, la carga finaliza cuando el usuario ingresa el cero. Determinar

a) Porcentaje que representan los números divisibles por 3 sobre el total de números ingresados en la secuencia

b) Determinar la cantidad de números que son el cuadrado del número anterior

c) Determinar la posición del mayor elemento impar de la secuencia

```python
print('Secuencia de numeros')
print('=' * 80)

cn = cnd3 = cnca = mayor = pos =0
primero = True
numero = int(input('Ingrese el primer numero de la serie (Con cero finaliza): '))
while numero != 0:
    cn += 1
    if numero % 3 == 0:
        cnd3 += 1

    #Aqui se puede reemplazar de las siguientes maneras haciendo al inicio import math
    # if cn > 1 and int(math.sqrt(numero)) == numero_anterior:
    # if cn > 1 and numero == numero_anterior ** 2:
    if cn > 1 and int(numero ** 0.5) == numero_anterior:
        cnca += 1

    if numero % 2 != 0:
        if primero:
            mayor = numero
            pos = 1
            primero = False
        else:
            if numero > mayor:
                mayor = numero
                pos = cn

    numero_anterior = numero
    numero = int(input('Ingrese otro numero de la secuencia: '))

print('_' * 80)
print('Presentacion de resultados')

if cn != 0:
    por = cnd3 * 100 / cn
    print('Hay', cnd3, 'numeros divisibles por 3 en la secuencia y representan el', round(por,2),'% del total de numeros')
    print('La cantidad de numeros que son el cuadrado del anterior son', cnca)
    print('El mayor numero impar es', mayor, 'y se encuentra en la posicion', pos)
else:
    print('No hay numero procesados')
```

### **2. Secuencia de n números**

Ingresar una secuencia de n números, de a uno por vez. El valor de n se ingresa por teclado, validar que sea mayor a 0. Determinar:

a) Cuántos números ingresados terminan en 5

b) La cantidad de veces que aparece el primer número ingresado por el usuario en la secuencia

c) Cuántos números ingresados son mayores al anterior

```python
print('Secuencia de numeros')
print('=' * 80)

cn5 = cn = cprimero = cma = primer_numero = numero_anterior = 0
numero = int(input('Ingrese el primer numero de la serie (finaliza con 0): '))
while numero != 0:
    cn += 1
    if cn == 1:
        primer_numero = numero
    else:
        if numero == primer_numero:
            cprimero += 1

        if numero > numero_anterior:
            cma += 1

    if numero % 10 == 5:
        cn5 += 1

    numero_anterior = numero
    numero = int(input('Ingrese otro numero de la secuencia: '))

print('_' * 80)
print('Presentacion de resultados')
print('Hay', cn5, 'numeros que terminan con cinco')
print('Aparece', cprimero, 'veces el primer numero de la secuencia')
print('Hay', cma, 'numeros que son mayores al anterior')
```

### **3. Secuencia numérica II**

Ingresar un secuencia de números, de a uno por vez, la carga finaliza cuando el usuario ingresa el cero. Determinar:

a) El promedio de los números que son múltiplos de 6

b) Cantidad de números que son divisor exacto del anterior

c) Indicar la cantidad de veces que se generó una secuencia ascendente de 3 o más números impares

```python
print("Secuencia de numeros")
print("=" * 80)

cn = suma_multiplos_6 = cant_multiplos_6 = multiplos_anterior = 0
secuencia_ascendente = cantidad_secuencias = 0
es_ascendente = False
num_anterior = 0
numero = int(input("Ingrese un numero (la carga finaliza cuando ingrese 0): "))
while numero != 0:

    cn += 1
    if numero % 6 == 0:
        suma_multiplos_6 += numero
        cant_multiplos_6 += 1

    if cn > 1:
        if num_anterior % numero == 0:
            multiplos_anterior += 1

        if num_anterior % 2 != 0 and numero % 2 != 0 and numero > num_anterior:
            secuencia_ascendente += 1
        else:
            if secuencia_ascendente >= 2:
                cantidad_secuencias += 1
            secuencia_ascendente = 0

    num_anterior = numero
    numero = int(input("Ingrese otro numero: "))

print('Hay', cant_multiplos_6, 'numeros en la secuencia que son multiplos de 6')
print('Hay', cantidad_secuencias, 'secuencias ascendentes de numeros impares '
                                  'en la secuencia de numeros')
print('Hay', multiplos_anterior, 'numeros que son divisor exacto del numero '
                                 'anterior')
```
