 Ficha 09: Subproblemas y funciones

### 1. Sílaba "mo"

Desarrollar un programa en Python que permita cargar por teclado un texto completo (analizar dos opciones: una es cargar todo el texto en una variable de tipo cadena de caracteres y recorrerla con un for iterador; y la otra es cargar cada caracter uno por uno a través de un while). Siempre se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar cuántas palabras tenían más de 4 letras.

b) Determinar cuántas palabras tenían al menos una vez la letra "x" o la letra "y".

c) Determinar el promedio de letras por palabra en todo el texto.

d) Determinar cuántas palabras contuvieron sólo una vez la expresión "mo".

---

*Ejemplo: 'el mono momoxy toca el xilofon.'*

---

*Palabras con más de 4 letras: 2*  
*Palabras tenían al menos una vez la letra "x" o la letra "y": 2*  
*El promedio de letras por palabra en todo el texto es: 4.17*  
*Determinar cuántas palabras contuvieron sólo una vez la expresión "mo": 1*

```python
print('Análisis de Texto')
print('*' * 80)

#Inicialización
letras_pal = 0
palabras_mas4 = 0
tieneXY = False
palabras_XY = 0
letras = 0
palabras = 0
anterior = None
cantMO = 0
palabras_MO = 0

#Carga de datos y proceso
texto = input('Ingrese el texto, separando palabras con un espacio y terminando con punto:')
for letra in texto:
    if letra == ' ' or letra == '.':
        #La longitud es mayor a 4?
        if letras_pal > 4:
            palabras_mas4 += 1
        #Contar si tiene X o Y
        if tieneXY == True:
            palabras_XY  += 1
        #Contar la palabra si ya se cargó algún caracter
        if letras >0:
            palabras += 1
        #Contar la palabra si tiene un solo MO
        if cantMO == 1:
            palabras_MO += 1
        #Reiniciar datos de la palabra
        letras_pal = 0
        tieneXY = False
        cantMO = 0
    else:
        #Procesando palabra
        letras_pal += 1
        #Detectar X o Y
        if letra == 'x' or letra == 'y':
            tieneXY = True
        #Contar todas las letras del texto
        letras += 1
        #Detectar la expresión MO
        if letra == 'o' and anterior == 'm':
            cantMO += 1
    anterior = letra

#Resultados
print('*' * 80)
print('Palabras con más de 4 letras:',palabras_mas4)
print('Palabras tenían al menos una vez la letra "x" o la letra "y":',palabras_XY)
if palabras == 0:
    promedio = 0
else:
    promedio = round(letras / palabras, 2)
print('El promedio de letras por palabra en todo el texto es:',promedio)
print('Determinar cuántas palabras contuvieron sólo una vez la expresión "mo":',palabras_MO)
```

```python
#1.2. Solución con funciones
__author__ = 'Catedra de Algoritmos y Estructuras de Datos'

def calcular_promedio(suma,cantidad):
    if cantidad == 0:
        promedio = 0
    else:
        promedio = round(suma / cantidad, 2)
    return promedio

def test ():
    print('Análisis de Texto')
    print('*' * 80)

    #Inicialización
    letras_pal = 0
    palabras_mas4 = 0
    tieneXY = False
    palabras_XY = 0
    letras = 0
    palabras = 0
    anterior = None
    cantMO = 0
    palabras_MO = 0

    #Carga de datos y proceso
    texto = input('Ingrese el texto a analizar, separando las palabras con un espacio y terminando con punto: ')
    for letra in texto:
        if letra == ' ' or letra == '.':
            #La longitud es mayor a 4?
            if letras_pal > 4:
                palabras_mas4 += 1
            #Contar si tiene X o Y
            if tieneXY == True:
                palabras_XY  += 1
            #Contar la palabra si ya se cargó algún caracter
            if letras >0:
                palabras += 1
            #Contar la palabra si tiene un solo MO
            if cantMO == 1:
                palabras_MO += 1
            #Reiniciar datos de la palabra
            letras_pal = 0
            tieneXY = False
            cantMO = 0
        else:
            #Procesando palabra
            letras_pal += 1
            #Detectar X o Y
            if letra == 'x' or letra == 'y':
                tieneXY = True
            #Contar todas las letras del texto
            letras += 1
            #Detectar la expresión MO
            if letra == 'o' and anterior == 'm':
                cantMO += 1
        anterior = letra

    #Resultados
    print('*' * 80)
    print('Palabras con más de 4 letras:',palabras_mas4)
    print('Palabras tenían al menos una vez la letra "x" o la letra "y":',palabras_XY)
    promedio = calcular_promedio(letras,palabras)
    print('El promedio de letras por palabra en todo el texto es:',promedio)
    print('Determinar cuántas palabras contuvieron sólo una vez la expresión "mo":',palabras_MO)

test()
```

### 2. Secuencia 1, 2, 3

Desarrollar un programa en Python que permita cargar por teclado una sucesión de números, uno por uno. Siempre se supone que el usuario cargará un 0(cero) para indicar el final del proceso de carga. El cero no debe considerarse un dato a procesar. El programa debe:

a) Determinar cuántos de los números ingresados eran divisibles por 4.

b) Determinar el mayor de los números impares ingresados.

c) Determinar cuántas veces se ingresó el primero de los números (cuente al primero).

d) Determinar cuántas veces se ingresó un 1, seguido de un 2, y seguido a su vez de un 3. Por ejemplo: en la sucesión: 3, 6, 1, 2, 3, 7, 8, 2, 3, 1, 2, 3, 0 ocurrió dos veces.

```python
# titulo general...
print('Deteccion de secuencia 1-2-3')
print('Carga de la secuencia, terminando en 0(cero)...')

# inicializacion de flags y contadores...
# contador de números ingresados...
cn = 0

# contador de números divisibles por 4...
cd4 = 0

# contador de veces que entro 1-2-3...
c123 = 0

# el mayor de los impares...
myi = None

# el primero de todos los numeros...
prim = None

# cuantas veces entro el primero de todos?...
cvp = 0

# flag: paso el primero de los impares?...
spi = False

# flag: el ultimo fue un 1?...
s1 = False

# flag: el ultimo fue un 2 e inmediatamente paso un 1?...
s12 = False

# carga del primer numero...
num = int(input('Numero (ingrese un 0(cero) para terminar): '))

# ciclo de carga para procesar le secuencia...
while num != 0:
    # contar el número actual...
    cn += 1

    # 1.) contar divisibles por 4...
    if num % 4 == 0:
        cd4 += 1

    # 2.) determinar el mayor de los impares...
    if num % 2 == 1:
        if not spi:
            myi = num
            spi = True
        elif num > myi:
            myi = num

    # 3.) determinar cuantas veces entro el primero de todos...
    if cn == 1:
        prim = num
    if num == prim:
        cvp += 1

    # 4.) determinar cuantas veces entro la secuencia 1-2-3...
    if num == 1:
        s1 = True
        s12 = False
    else:
        if num == 2 and s1:
            s12 = True
        else:
            if num == 3 and s12:
                c123 += 1

            s12 = False
        s1 = False

    # carga del siguiente numero...
    num = int(input('Otro (ingrese un 0(cero) para terminar): '))

# analisis de los resultados finales...
print('1. Cantidad de numeros divisibles por 4:', cd4)
print('2. Mayor de los impares:', myi)
print('3. El primero fue el', prim, 'y se ingreso:', cvp, 'veces')
print('4. Cantidad de veces que se formo la secuencia 1-2-3:', c123)
```

```python
def test():
    # titulo general...
    print('Deteccion de secuencia 1-2-3')
    print('Carga de la secuencia, terminando en 0(cero)...')

    # inicializacion de flags y contadores...
    # contador de números ingresados...
    cn = 0

    # contador de números divisibles por 4...
    cd4 = 0

    # contador de veces que entro 1-2-3...
    c123 = 0

    # el mayor de los impares...
    myi = None

    # el primero de todos los numeros...
    prim = None

    # cuantas veces entro el primero de todos?...
    cvp = 0

    # flag: paso el primero de los impares?...
    spi = False

    # flag: el ultimo fue un 1?...
    s1 = False

    # flag: el ultimo fue un 2 e inmediatamente paso un 1?...
    s12 = False

    # carga del primer numero...
    num = int(input('Numero (ingrese un 0(cero) para terminar): '))

    # ciclo de carga para procesar le secuencia...
    while num != 0:
        # contar el número actual...
        cn += 1

        # 1.) contar divisibles por 4...
        if num % 4 == 0:
            cd4 += 1

        # 2.) determinar el mayor de los impares...
        if num % 2 == 1:
            if not spi:
                myi = num
                spi = True
            elif num > myi:
                myi = num

        # 3.) determinar cuantas veces entro el primero de todos...
        if cn == 1:
            prim = num
        if num == prim:
            cvp += 1

        # 4.) determinar cuantas veces entro la secuencia 1-2-3...
        if num == 1:
            s1 = True
            s12 = False
        else:
            if num == 2 and s1:
                s12 = True
            else:
                if num == 3 and s12:
                    c123 += 1

                s12 = False
            s1 = False

        # carga del siguiente numero...
        num = int(input('Otro (ingrese un 0(cero) para terminar): '))

    # analisis de los resultados finales...
    print('1. Cantidad de numeros divisibles por 4:', cd4)
    print('2. Mayor de los impares:', myi)
    print('3. El primero fue el', prim, 'y se ingreso:', cvp, 'veces')
    print('4. Cantidad de veces que se formo la secuencia 1-2-3:', c123)


# script principal...
# ... solo invocar a test()...
test()

```

### 3. Secuencia 5, 5

Desarrollar un programa en Python que permita cargar por teclado una sucesión de números, uno por uno. Siempre se supone que el usuario cargará un 0(cero) para indicar el final del proceso de carga. El cero no debe considerarse un dato a procesar. El programa debe:

a) Determinar cuántos de los números ingresados eran mayores que *n1* y menores que *n2* (cargar previamente por teclado los números *n1* y *n2*).

b) Determinar el porcentaje que el total de números calculado en el punto 1 representa en el total de números cargados.

c) Determinar si en algún momento se ingresó un número impar seguido inmediatamente de un par. No importa cuántas veces ocurrió: sólo indicar si al menos una vez pasó.

d) Determinar cuántas veces se ingresó un 5 seguido inmediatamente de otro 5. Por ejemplo: en la sucesión: 3, 6, 5, 5, 7, 5, 2, 5, 9, 5, 5, 0 ocurrió dos veces.

```python
def calcular_porcentaje(valor, total):
    porc = 0
    if total > 0:
        porc = round(valor * 100 / total, 2)
    return porc


def es_par(numero):
    resto = numero % 2
    if resto == 0:
        return True
    else:
        return False

def test():
    print('Analisis de Secuencia 5,5')
    print('-' * 80)

    n1 = int(input('Ingrese la cota minima del intervalo a definir: '))
    n2 = int(input('Ingrese la cota maxima del intervalo a definir: '))

    cant_num_intervalo = cant_numeros = cant_secuencia_5 = 0
    hay_par_impar = False
    anterior = 0
    numero = int(input('Ingrese un numero de la secuencia, con cero termina: '))
    while numero != 0:
        cant_numeros += 1
        if n1 < numero < n2:
            cant_num_intervalo += 1

        if cant_numeros > 1:
            if not es_par(anterior) and es_par(numero):
                hay_par_impar = True

            if anterior == 5 and numero == 5:
                cant_secuencia_5 += 1
        anterior = numero
        numero = int(input('Ingrese otro numero de la secuencia: '))

    porc = calcular_porcentaje(cant_num_intervalo, cant_numeros)
    print('La cantidad de numeros dentro del intevalo [', n1, ':', n2, '] es: ', cant_num_intervalo, sep='')
    print('El porcentaje de numero en el intervalo sobre el total de numeros es: ', porc, '%', sep='')
    print('La cantidad de secuencia 5,5 ingresada es:', cant_secuencia_5)
    if hay_par_impar:
        print('Se ha ingreseado al menos un numero impar seguido de un par')

test()
```

### 4. Inicio con sílaba "pa"

Desarrollar un programa en Python que permita cargar por teclado un texto. Siempre se supone que usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe determinar: 

a) La cantidad de palabras que comienzan con la expresión "pa" y termina con la letra "n" 

c) La cantidad de palabras que presentan mas de dos vocales a partir de la tercera letra de la palabra 

d) El porcentaje que representa la cantidad de palabras del punto anterior respecto de la cantidad de total de palabras del texto 

e) Cantidad de palabras de mas de 5 letras

```python
def es_vocal(letra):
    vocales = 'aeiouáéíóú'
    return letra in vocales

def calcular_porcentaje(muestra, total):
    porc = 0
    if total > 0:
        porc = round(muestra * 100 / total, 2)
    return porc

def main():
    print('Analisis de Texto - Silabas \"pa\"')
    print('-' * 80)

    cont_letras = cant_pal_pa = cant_vocales = cant_pal_dosvocales = 0
    cant_palabras = cant_pal_5letras = 0

    tiene_p = tiene_pa = tiene_n = False
    texto = input('Ingrese el texto a analizar, debe finalizar con punto: ')
    for letra in texto:
        if letra == ' ' or letra == '.':
            if cont_letras > 0:
                cant_palabras += 1
                if tiene_pa and tiene_n:
                    cant_pal_pa += 1

                if cant_vocales > 2:
                    cant_pal_dosvocales += 1

                if cont_letras > 5:
                    cant_pal_5letras += 1

            tiene_p = False
            tiene_pa = False
            cant_vocales = 0
            cont_letras = 0
        else:
            cont_letras += 1
            if cont_letras == 1 and letra == 'p':
                tiene_p = True
            else:
                if tiene_p and letra == 'a':
                    tiene_pa = True
                tiene_p = False

            if cont_letras > 3:
                if es_vocal(letra):
                    cant_vocales += 1

            tiene_n = False
            if letra == 'n':
                tiene_n = True

    porcentaje = calcular_porcentaje(cant_pal_pa, cant_palabras)
    print('La cantidad de palabras que empiezan con \"pa\" y '
          'terminan con \"s\" es:', cant_pal_pa)
    print('El porcentaje de la cantidad anterior sobre el total '
          'del texto es: ', porcentaje, '%', sep='')
    print('La cantidad de palabras con mas de 2 vocales a partir '
          'de la tercera letra es:', cant_pal_dosvocales)
    print('La cantidad de palabras con mas de cinco letras es:',
          cant_pal_5letras)

main()
```

### 5. Secuencia en rango

Desarrollar un programa de Python que permita cargar por teclado un secuencia de números, uno por uno. Siempre se supone que el usuario cargará un 0(cero) para indicar el final del proceso de carga. El cero no debe considerarse un dato a procesar. El programa debe: 

a) Determinar cuantos números se encuentran en el rango definido por 2 números p y q previamente ingresados (validar que los números que definen el rango son mayores a cero) 

b) Determinar la cantidad de veces que se ingresaron 2 números contiguos pares. 

c) Determinar la cantidad de números que son múltiplos del primer numero de la secuencia 

d) Determinar el porcentaje que representa la cantidad del primer punto sobre el total de números de la secuencia

```python
def validar_mayor(valor, mensaje='Ingrese un numero: '):
    numero = 0
    while numero <= valor:
        numero = int(input(mensaje))
        if numero <= valor:
            print('Error!!!! El numero debe ser mayor a ', valor)
    return numero


def porcentaje(total, cantidad):
    por = 0
    if total != 0:
        por = round(cantidad * 100 / total, 2)
    return por


def validar_rango():
    cota_inferior = validar_mayor(0, 'Ingrese la cota inferior de rango: ')
    cota_superior = validar_mayor(0, 'Ingrese la cota superior de rango: ')
    while cota_superior < cota_inferior:
        cota_superior = validar_mayor('Ingrese la cota superior de rango, debe ser mayor a la inferior: ')
    return cota_inferior, cota_superior


def es_multiplo(numero, divisor):
    resto = numero % divisor
    return resto == 0


def es_par(numero):
    return es_multiplo(numero, 2)


def test():
    
    print('Secuencia de Rangos')
    print('*' * 60)

    primer_numero = 0
    anterior = -1
    primero = True
    cantidad_rango = cant_pares_contig = cant_mult = cant_num = 0

    cota_inferior, cota_superior = validar_rango()

    numero = int(input('Ingresar un numero, la secuencia finaliza cuando ingrese el: '))
    while numero != 0:

        cant_num += 1
        if primero:
            primer_numero = numero
            primero = False
        else:
            if es_multiplo(numero, primer_numero) == 0:
                cant_mult += 1

        if cota_inferior <= numero <= cota_superior:
            cantidad_rango += 1

        if es_par(anterior) and es_par(numero) == 0:
            cant_pares_contig += 1

        anterior = numero
        numero = int(input('Ingrese el siguiente numero de la secuencia: '))

    print('-' * 60)
    print('Resultados')
    print('-' * 60)

    porc = porcentaje(cant_num, cantidad_rango)
    print('Hay', cantidad_rango, 'números se encuentran en el rango definido entre', cota_inferior, 'y', cota_superior)
    print('Y representa un', porc, '% del total de numeros de la serie')
    print(cant_pares_contig, 'veces que se ingresaron 2 números contiguos pares')
    print(cant_mult, 'números que son múltiplos del primer numero de la secuencia ')


test()
```

### 6. Sílaba "pe"

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. Se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar cuántas palabras tienen 3, 5 o 7 letras.

b) Determinar la cantidad de palabras con más de tres letras, que tienen una vocal en la tercera letra. 

c) Determinar el porcentaje de palabras que tienen sólo una o dos vocales sobre el total de palabras del texto. 

d) Determinar la cantidad de palabras que contienen más de una vez la sílaba "pe".

### 7. Secuencia promedio de pares

Se pide desarrollar un programa en Python controlado por un menú de opciones. Ese menú debe permitir gestionar las siguientes tareas, siempre usando funciones que acepten parámetros y/o retornen valores en cada situación en que se considere apropiado:

a) Cargar una sucesión de numeros enteros y positivos (validar que efectivamente cada número que se cargue sea mayor a cero). La carga finaliza cuando se ingresa un cero. Mostrar la cantidad de numeros de la sucesión cargada que son multiplos del primer numero de la secuencia.

b) Ingresar por teclado dos números *p* y *q* que definen los límites de un intervalo *[p, q]* (validar que *0 < p < q*) y una sucesión de *n* números (también cargando *n* por teclado y validando que *n > 0*) Determine cuántos de los números de la sucesión cargada están fuera del intervalo y cuántos están dentro del intervalo, e indicar también cuántos de los números cargados eran pares y estaban dentro del intervalo dado.

c) Cargar una secuencia de números enteros positivos (validar que efectivamente cada número que se cargue sea mayor a cero).  La carga debe terminar cuando se ingrese un número mayor a 100. Determine si en la secuencia se ingresaron dos números contiguos que sean pares. Si es así muestre el promedio de todos los números pares que se hayan ingresado. Si no, informe que no se ingresaron números contiguos pares. Ejemplo: en la secuencia {1, 2, 3, 6, 4, 7, 8} hay al menos un dos números contiguos que son pares (el 6 y el 4) y en este caso, el promedio de todos los pares de la secuencia es (2 + 6 + 4 + 8) / 4 = 20/4 = 5. Pero en esta secuencia: {1, 2, 5, 7, 8, 9, 3, 6, 1} no hay números contiguos pares.

```python
def validar_mayor(valor, mensaje):
    numero = int(input(mensaje))
    while numero <= valor:
        print('Error!!! El numero debe ser mayor a', valor)
        numero = int(input(mensaje))

    return numero


def es_multiplo(numero, divisor):
    paridad = numero % divisor
    if paridad == 0:
        return True
    else:
        return False


def multiplos_primer_valor():
    cantidad = 0
    numero = validar_mayor(-1, 'Ingrese un numero de la secuencia (finaliza con cero): ')
    es_primero = True
    primero = -1
    while numero != 0:
        if es_primero:
            es_primero = False
            primero = numero
        else:
            if es_multiplo(numero, primero):
                cantidad += 1
        numero = validar_mayor(-1, 'Ingrese otro numero de la secuencia: ')
    return cantidad

def leer_intervalo():
    p = validar_mayor(0, 'Ingrese la cota inferior del intervalo: ')
    q = validar_mayor(0, 'Ingrese la cota superior del intervalo: ')
    while q < p:
        print('El Intervalo definido no es correcto, reingrese los valores')
        p = validar_mayor(0, 'Ingrese la cota inferior del intervalo: ')
        q = validar_mayor(0, 'Ingrese la cota superior del intervalo: ')
    return p, q


def es_par(numero):
    return es_multiplo(numero, 2)


def analizar_intervalo(p, q, n):
    can_fuera = can_dentro, can_pares = 0
    for i in range(n):
        numero = int(input('Ingrese un numero a analizar: '))
        if numero < p or numero > q:
            can_fuera += 1
        else:
            can_dentro += 1
            if es_par(numero):
                can_pares += 1

    return can_fuera, can_dentro, can_pares


def calcular_promerio(dividendo, divisor):
    prom = 0
    if divisor != 0:
        prom = dividendo / divisor
    return round(prom, 2)


def analizar_pares_contiguos():
    numero = validar_mayor(0, 'Ingrese un numero de la secuencia: ')
    anterior = -1
    hay_pares_contiguos = False
    acumulador = contador = 0
    while numero < 100:
        if es_par(numero):
            contador += 1
            acumulador += numero

        if es_par(anterior) and es_par(numero):
            hay_pares_contiguos = True

        anterior = numero
        numero = validar_mayor(0, 'Ingrese un numero de la secuencia: ')

    prom = 0
    if hay_pares_contiguos:
        prom = calcular_promerio(acumulador, contador)
    return hay_pares_contiguos, prom

def test():
    menu = 'Menu de Opciones\n' \
           '1 - Secuencia de multiplos\n' \
           '2 - Analisis de rango\n' \
           '3 - Promedio de Pares\n' \
           '4 - Salir\n'\
           'Ingrese su opcion: '

    opcion = - 1
    while opcion != 4:
        opcion = int(input(menu))
        if opcion == 1:
            cant_numero = multiplos_primer_valor()
            print('La cantidad de numeros multiplos del primero son:', cant_numero)
        elif opcion == 2:
            p, q = leer_intervalo()
            n = validar_mayor(0, 'Ingrese la cantidad de numeros a procesar: ')

            cant_fuera, cant_dentro, cant_pares_dentro = analizar_intervalo(p, q, n)

            print('La cantidad de valores fuera de [', p, ':', q, '] son: ', cant_fuera, sep='')
            print('La cantidad de valores dentro de [', p, ':', q, '] son: ', cant_dentro, sep='')
            print('La cantidad de valores pares dentro de [', p, ':', q, '] son: ',
                  cant_pares_dentro, sep='')
        elif opcion == 3:
            hay_pares, promedio = analizar_pares_contiguos()
            if hay_pares:
                print('En la secuencia hubo pares contiguos y su promedio es:', promedio)
            else:
                print('En la secuencia no hubo pares contiguos')


test()
```

### 8. Menú de repetitivas

Desarrollar un programa controlado por menú de opciones, que permita:

a) Tablas: ingresar por teclado un valor positivo entre 1 y 10 (validarlo). Mostrar la tabla de multiplicar correspondiente a dicho número. (Por ej: si se ingresa 3, mostrar 3x1=3, 3x2=6 etc.)  

b) Mayor y menor: ingresar por teclado una sucesión de números positivos (validar), que termina cuando se ingresa 0. Informar mayor y menor valor de la sucesión.

c) Múltiplos: ingresar por teclado dos valores a y b, siendo a positivo y b mayor que a (validarlo). Sumar todos los múltiplos de a comprendidos en el intervalo [a,b]

d) Texto: ingresar por teclado un texto terminado en un punto (validar esto), cuyas palabras se separan por un único espacio. Informar cuántas palabras terminan en vocal y qué porcentaje representan sobre el total de palabras del texto.

```python
def validar_entre(minimo, maximo):
    mensaje = 'Ingrese un valor entre ' + str(minimo) + ' y ' + str(maximo) + ': '
    valor = int(input(mensaje))
    while valor <= minimo or valor >= maximo:
        valor = int(input('Inválido! ' + mensaje))
    return valor


def validar_mayor_que(minimo):
    mensaje = 'Ingrese un valor mayor que ' + str(minimo) + ': '
    valor = int(input(mensaje))
    while valor <= minimo:
        valor = int(input('Inválido! ' + mensaje))
    return valor


def validar_punto_final():
    mensaje = 'Ingrese un texto terminado en punto: '
    texto = input(mensaje)
    while texto[-1] != '.':
        texto = input('Inválido! ' + mensaje)
    return texto


def impares():
    num = validar_entre(0,11)
    for i in range(11):
        print(num,'x',i,'=',num*i)

def mayor_y_menor():
    num = validar_mayor_que(-1)
    primero = True
    may = 0
    men = 0
    while num!= 0:
        if primero:
            may = num
            men = num
            primero = False
        else:
            if num > may:
                may = num
            if num < men:
                men = num
        num = validar_mayor_que(-1)
    return may, men


def multiplos():
    a = validar_mayor_que(0)
    b = validar_mayor_que(a)
    suma = 0
    for multiplo in range(a,b,a):
        suma += multiplo
    return suma


def calcular_porcentaje(valor, total):
    if total == 0:
        return 0
    else:
        return round(valor * 100 / total, 2)

def texto():
    texto = validar_punto_final()
    #Procesar texto
    vocales = 'aeiou'
    pal_vocal = 0
    palabras = 0
    anterior = ''
    for letra in texto:
        if letra == '.' or letra == ' ':
            if anterior != '':
                palabras += 1
            if anterior in vocales:
                pal_vocal += 1
        else:
        anterior = letra
    #Calcular porcentaje
    porc = calcular_porcentaje(pal_vocal,palabras)
    return pal_vocal, porc


def  test():
    opcion = -1
    while opcion != 0:
        print('*'*80)
        print('OPCIONES REPETITIVAS')
        print('1-Impares')
        print('2-Mayor y menor')
        print('3-Múltiplos')
        print('4-Texto')
        print('0-Salir')
        opcion = int(input('\nIngrese su opción: '))
        if opcion == 1:
            impares()
        elif opcion == 2:
            may, men = mayor_y_menor()
            print('El mayor valor de la serie fue',may)
            print('El menor valor de la serie fue',men)
        elif opcion == 3:
            suma = multiplos()
            print('La suma de los múltiplos es',suma)
        elif opcion == 4:
            pal, porc = texto()
            print('Se detectaron',pal,'palabras con vocal, y son el',porc,'del texto')
        print('*'*80)


test()
```

### 9. Juego de Cartas

Desarrollar un programa para implementar un juego de cartas de la baraja española. Es una competencia de n rondas entre 2 jugadores (n se carga por teclado, validar)

En cada ronda, cada jugador recibe una carta (cuyo número y palo el programa deberá generar de forma aleatoria) y se define la ronda de la siguiente manera:

- El jugador que tenga la carta de mayor valor, se lleva ambas.
- Si las cartas son del mismo valor, se las lleva quien tenga una carta de oro.
- Si ambos tienen oro o ninguno lo tiene, cada jugador recupera su carta.

Los puntos de cada jugador se determinan sumando los valores de todas las cartas que ganó. Será triunfador el que tenga mayor puntaje total.

```python
import random

def validar_mayor_que(minimo, mensaje):
    num = int(input(mensaje))
    while num <= minimo:
        num = int(input('INVALIDO! ' + mensaje))
    return num


def generar_carta():
    palos = ('Copa', 'Basto', 'Espada', 'Oro')
    num = random.randint(1, 12)
    palo = random.choice(palos)
    return num,palo


def jugar(n):
    puntos1 = puntos2 = 0
    for ronda in range(n):
        print('\nRONDA',ronda)

        carta1 = generar_carta()
        print('Jugador 1 obtiene', carta1)

        carta2 = generar_carta()
        print('Jugador 2 obtiene', carta2)

        suma = carta1[0] + carta2[0]
        if carta1[0] > carta2[0]:
            puntos1 += suma
        elif carta2[0] > carta1[0]:
            puntos2 += suma
        else:
            if carta1[1] == 'Oro' and carta2[1]!='Oro':
                puntos1 += suma
            elif carta1[1] != 'Oro' and carta2[1]=='Oro':
                puntos2 += suma
            else:
                puntos1 += carta1[0]
                puntos2 += carta2[0]
        print('Puntajes: ',puntos1,'a',puntos2)

    return puntos1,puntos2


def mostrar_resultado(puntos1, puntos2):
    if puntos1 > puntos2:
        print('¡El Jugador 1 es el ganador!')
    elif puntos2 > puntos1:
        print('¡El Jugador 2 es el ganador!')
    else:
        print('¡Los jugadores empataron!')


def principal():
    print('JUEGO DE CARTAS')
    print('*' * 80)
    n = validar_mayor_que(0,'Ingrese rondas a jugar: ')
    puntos1, puntos2 = jugar(n)
    print('*' * 80)
    mostrar_resultado(puntos1,puntos2)


if __name__ == '__main__':
    principal()
```

### 10. Portal de empleo

Un conocido portal de empleo requiere un programa para validar las búsquedas que se cargan en su página. Por cada búsqueda se requiere:

- CUIT: validar que sea un texto compuesto por 13 números separados por guiones de la siguiente manera: 00-00000000-0
- Descripción de la búsqueda: un texto donde cada palabra se separa con un espacio y termina con punto. Debe tener un máximo de 60 caracteres y un mínimo de 3 palabras. Ninguna palabra debe contener dos mayúsculas seguidas.
- Salario ofrecido: controlar que sea un valor mayor a 0

Si todos los datos son válidos, mostrar el aviso completo. En caso contrario, informar que no es posible mostrarlo.

Para terminar, consultar al usuario si desea cargar otro aviso o salir del programa.

```python
def validar_cuit(cuit):
    # CUIT: un texto compuesto por 13 números
    # separados por guiones de la siguiente manera: 00-00000000-0
    valido = False
    cant_numeros = 0
    if len(cuit) == 13:
        if cuit[2] == '-' and cuit[11] == '-':
            for car in cuit:
                if car in '0123456789':
                    cant_numeros += 1
            # Controlo si todos los que no son guiones, son digitos
            if cant_numeros == 11:
                valido = True
    return valido


def es_mayuscula(letra):
    if letra >= 'A' and letra <= 'Z':
        return True
    else:
        return False


def validar_descripcion(descripcion):
    # Descripción de la búsqueda: un texto donde
    # cada palabra se separa con un espacio y termina con punto.
    # Debe tener un máximo de 60 caracteres y un mínimo de 3 palabras.
    # Ninguna palabra debe contener 2 mayúsculas seguidas.
    valida = False
    cant_palabras = 0
    anterior = ''
    tiene_mayusc_seguidas = False
    if len(descripcion) <= 60:
        for letra in descripcion:
            # Contamos las palabras
            if letra == ' ' or letra == '.':
                cant_palabras += 1
            else:
                # Controlamos mayusculas seguidas
                if es_mayuscula(letra) and es_mayuscula(anterior):
                    tiene_mayusc_seguidas = True
            anterior = letra
        # Controlamos cantidad de palabras
        if cant_palabras >= 3:
            # Controlamos que no haya mayusculas seguidas
            if tiene_mayusc_seguidas == False:
                valida = True
    return valida


def validar_salario(salario):
    # Salario ofrecido: un valor mayor a 0
    if salario > 0:
        valido = True
    else:
        valido = False
    return valido

def principal():
    rta = 'S'
    while rta == 'S':
        print('PORTAL DE EMPLEOS')
        # Datos
        cuit_empleador = input('Ingrese cuit: ')
        # Proceso
        if validar_cuit(cuit_empleador):
            descripcion = input('Ingrese descripcion de la busqueda: ')
            if validar_descripcion(descripcion):
                salario = int(input('Ingrese salario ofrecido (mayor a 0): '))
                if validar_salario(salario):
                    # Mostramos el aviso
                    print('=' * 50)
                    print('AVISO')
                    print('El empleador', cuit_empleador, 'te esta buscando!')
                    print('Busqueda:', descripcion)
                    print('El salario ofrecido es de $', salario)
                    print('=' * 50)
                else:
                    print('El salario no es valido')
            else:
                print('La descripcion no es valida')
                print('Debe tener un máximo de 60 caracteres y un mínimo de 3 palabras.')
                print('Ninguna palabra debe contener 2 mayúsculas seguidas.')
        else:
            print('El cuit no es valido')
            print('Debe ser un texto compuesto por 13 números separados por guiones')
            print('de la siguiente manera: 00-00000000-0')
        rta = input('Quiere cargar otro aviso? (S/N) ')

    print('Programa terminado')


principal()
```

```python
def validar_cuit(cuit):
    # Proceso
    valido = False
    cant_nums = 0
    if len(cuit) == 13:
        if cuit[2] == '-' and cuit[-2] == '-':
            for car in cuit:
                if car >= '0' and car <= '9':
                    cant_nums += 1
            if cant_nums == 11:
                valido = True
            else:
                print('Los caracteres del CUIT no son todos numéricos')
        else:
            print('Los guiones del CUIT no son correctos')
    else:
        print('La longitud del CUIT es incorrecta')
    # Resultado
    return valido


def es_mayuscula(letra):
    if letra >= 'A' and letra <= 'Z':
        return True
    else:
        return False


def validar_descripcion(descripcion):
    valida = False
    cant_pal = 0
    mayusc_seg = False
    anterior = ''
    if len(descripcion) <= 60:
        for letra in descripcion:
            if letra == ' ' or letra == '.':
                cant_pal += 1
            if es_mayuscula(letra) and es_mayuscula(anterior):
                mayusc_seg = True
            anterior = letra
        if cant_pal >= 3:
            if mayusc_seg == False:
                valida = True
            else:
                print('Descripción inválida -  Tiene dos mayúsculas seguidas')
        else:
            print('Descripción inválida -  Tiene menos de 3 palabras')
    else:
        print('Descripción inválida - Tiene más de 60 caracteres')
    return valida


def validar_salario(salario):
    valido = False
    if salario > 0:
        valido = True
    else:
        print('El salario no puede ser menor que cero')
    return valido


def principal():
    rta = 'S'
    while rta == 'S':
        print('-' * 80)
        print('PORTAL DE EMPLEO')
        # Datos y proceso
        cuit = input('Ingrese el CUIT: ')
        ok = validar_cuit(cuit)
        if ok:
            descripcion = input('Ingrese la descripcion: ')
            ok = validar_descripcion(descripcion)
            if ok:
                salario = float(input('Ingrese el salario: '))
                ok = validar_salario(salario)
                if ok:
                    print('La empresa ', cuit, 'busca', descripcion, '- Salario ofrecido $', salario)
                    print('-' * 80)
        rta = input('Desea cargar otro? S/N: ')


if __name__ == '__main__':
    principal()
```

### 11. Inicio y fin con vocal

Se solicita crear un programa que permita ingresar un texto, las palabras se encontrarán separadas únicamente por espacios en blanco y el mismo debe finalizar con un punto. En base a ese texto determinar:

a) La cantidad de palabras que comienzan y terminan en vocal

b) La cantidad de palabras que comienzan con la misma letra que terminó la palabra anterior

c) El porcentaje que representa el punto *a)* sobre el total de palabras del texto

```python
print('Analisis de Texto')
print('=' * 80)

vocales = 'aeiouAEIOU'
texto = input('Ingrese el texto a analizar, separados por blancos y termina en punto: ')
cp = cl = cpev = cpeucpa = 0
emp_vocal = False
ult_car_pal = car_ant = ''

for caracter in texto:
    cl += 1
    if caracter == ' ' or caracter == '.':
        if cl > 0:
            cp += 1
            ult_car_pal = car_ant
            if emp_vocal and car_ant in vocales:
                cpev += 1
                emp_vocal = False
        cl = 0

    if cl == 1:
        if caracter in vocales:
            emp_vocal = True

        if ult_car_pal == caracter:
            cpeucpa += 1
            ult_car_pal = ''

    car_ant = caracter

if cp > 0:
    por = cpev * 100 / cp

    print('Hay', cpev, 'palabras que empiezan y terminan en vocales que representan el', por, '% de palabras del texto')
    print('Hay', cpeucpa, 'palabras que comienzan con el ultimo caracter de la palabra anterior')
else:
    print('No se ingreso texto a analizar')
```

### 12. Sílaba 'li'

Se solicita crear un programa que permita ingresar un texto, las palabras se encontraran separadas únicamente por espacios en blanco y el mismo debe finalizar con un punto. En base a ese texto determinar:

a) Cantidad de palabras que comienzan con consonantes y terminan en vocales

b) Cantidad de palabras que poseen la secuencia ‘li’ a partir de la tercera letra de la palabra

c) Cantidad de palabras con menos de 4 letras y porcentaje que dicha cantidad representa sobre el total del texto

```python
print('Analisis de Texto')
print('=' * 80)

vocales = 'aeiouAEIOU'
clet = cpal = cpecv = palabras_li = palabras_menos_4 = 0
emp_conso = tiene_li = False
car_ant = ''
texto = input('Ingrese el texto a analizar, separados por blancos y termina '
              'en punto: ')
for caracter in texto:

    if caracter == ' ' or caracter == '.':
        if clet > 0:
            cpal += 1
            if emp_conso and car_ant in vocales:
                cpecv += 1
                emp_conso = False

            if tiene_li:
                palabras_li += 1
                tiene_li = False

            if clet < 4:
                palabras_menos_4 += 1
        clet = 0
    else:
        clet += 1
        if clet == 1:
            if caracter not in vocales:
                emp_conso = True

        elif clet >= 3:
            if car_ant == 'l' and caracter == 'i':
                tiene_li = True

    car_ant = caracter

if cpal > 0:
    print('Hay', cpecv, ' palabras en el texto que empiezan con consonante '
                        'y terminan con vocal')
    print('Hay', palabras_li, 'palabras en el texto que poseen la secuenci '
                              '"li" a partir de la tercer letra')
    por = palabras_menos_4 * 100 / cpal
    print('Hay', palabras_menos_4, 'palabras en el texto con menos de 4 '
                                   'letras y representan el', por,
                                   '% de palabras del texto')
else:
    print('No se ha ingresado un texto para analizar')
```

### 13. Silaba "ta"

El usuario ingresa una frase al comenzar el programa, la misma no puede tener longitud cero. La frase finaliza con un punto, y las palabras están separadas por espacios únicamente.  
Se debe mostrar:

a) Ver el porcentaje de vocales respecto del total de letras de la frase.

b) La longitud promedio de las palabras

c) La longitud de la palabra mas larga del texto

d) Cantidad de palabras que comienzan con "ta"

### 14. Longitudes Menores

Cargar por teclado una frase separada por espacios y termina con un punto (el cual no forma parte de la frase a procesar). Se debe establecer cuántas palabras de la frase están antecedidas por otra palabra de menor o igual longitud (la primer palabra de la frase nunca podrá ser contabilizada ya que no posee palabra antecesora).

Por ejemplo, la frase “Este es un ejercicio un poco complicado.” tiene 4 palabras cuya antecesora es igual o más corta en longitud (“un”, “ejercicio”, “poco”, “complicado”).

```python
print('Tratamiento de Caracteres, longitud de palabras')
print('-' * 90)


cl = 0
cl_previa = 0
cantidad_palabras = 0


texto = input('Ingrese el texto a procesar: ')
texto = texto.upper()

for car in texto:
    if car != ' ' and car != '.':
        cl += 1
    else:
        if cl_previa != 0 and cl_previa <= cl:
            cantidad_palabras += 1
        cl_previa = cl
        cl = 0

print('Resultados')
print('-' * 90)
print('Hay', cantidad_palabras, ' que son antecedidas por una de menor o igual longitud en el texto')

```

### 15. Sílaba "dre"

Desarrollar un programa en Python que permita cargar por teclado un texto completo. Siempre se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar cuántas palabras tenían exactamente 3 letras.

b) Determinar el porcentaje que las palabras del punto 1 representan en el total del palabras del texto.

c) Determinar cuántas palabras terminaban con la letra "s".

d) Determinar cuántas palabras contuvieron al menos una vez la expresión "dre".

```python
print('Analisis de texto con silabra dre')
print('-' * 80)

texto = input('Ingrese el texto a analizar, debe finalizar con punto: ')
anterior = ''
cont_letras = pal_3let = cant_pal = pal_terminan_s = pal_dre = 0
tiene_d = tiene_dr = tiene_dre = False
for letra in texto:
    if letra == ' ' or letra == '.':
        if cont_letras > 0:
            cant_pal += 1

            if cont_letras == 3:
                pal_3let += 1

            if anterior == 's':
                pal_terminan_s += 1

            if tiene_dre:
                pal_dre += 1

            tiene_dre = False
            cont_letras = 0
    else:
        cont_letras += 1
        if letra == 'd':
            tiene_d = True
            tiene_dr = False
        else:
            if letra == 'r' and tiene_d:
                tiene_dr = True
            else:
                if letra == 'e' and tiene_dr:
                    tiene_dre = True
                tiene_dr = False
            tiene_d = False
        anterior = letra


porc = 0
if cant_pal != 0:
    porc = round(pal_3let * 100 / cant_pal, 2)

print('Presentacion de Resultados')
print('-' * 80)
print('Cantidad de palabras con exactamente tres letras:', pal_3let)
print('La cantidad de palabras que terminan con \'s\' son:', pal_terminan_s)
print('La cantidad de palabras que contienen \'dre\' son:', pal_dre)
print('El porcentaje de palabra de tres letras respecto del total de palabras del texto es: ', porc, '%', sep='')

```

## Ficha 10: Programación modular

### 1. Sílaba "de" en la primera mitad

Desarrollar un programa en Python que permita cargar por teclado un texto completo. Siempre se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar cuántas palabras tenían al menos un caracter que era en realidad un dígito (un caracter entre '0' y '9').

b) Determinar cuántas palabras tenían 3 o menos letras, cuántas tenían 4 y hasta 6 letras, y cuántas tenían más de 6 letras.

c) Determinar la longitud de la palabra más larga del texto.

d) Determinar cuántas palabras contuvieron la expresión "de", pero en la primera mitad de la palabra.

```python
def is_digit(letra):
    digitos = '0123456789'
    return letra in digitos


def test():
    print('Analisis de Texto - Silaba \"de\" primera mitad')
    print('=' * 80)

    texto = input('Ingrese el texto a analizar, finaliza con punto: ')
    tiene_digito = tiene_d = tiene_de = False
    palabra_digito = pal_3letras = pal_4a6letras = pal_mas6letras = cant_letras = pal_demitad = 0
    mayor_longitud = posicion = 0

    for letra in texto:
        if letra == ' ' or letra == '.':

            if tiene_digito:
                palabra_digito += 1

            if cant_letras <= 3:
                pal_3letras += 1
            elif 4 <= cant_letras <= 6:
                pal_4a6letras += 1
            elif cant_letras > 6:
                pal_mas6letras += 1

            if cant_letras > mayor_longitud:
                mayor_longitud = cant_letras

            mitad = cant_letras // 2
            if tiene_de and 0 < posicion <= mitad:
                pal_demitad += 1

            tiene_de = tiene_d = False
            tiene_digito = False
            cant_letras = 0

        else:
            cant_letras += 1

            if is_digit(letra):
                tiene_digito = True

            if letra == 'd' and not tiene_de:
                tiene_d = True
            else:
                if letra == 'e' and tiene_d:
                    tiene_de = True
                    posicion = cant_letras
                tiene_d = False

    print('Presentacion de Resultados')
    print('-' * 80)
    print('La cantidad de palabras que contienen al menos un digito: ', palabra_digito)
    print('La cantidad de palabras que contienen hasta 3 letras es:', pal_3letras)
    print('La cantidad de palabras que contienen entre 4 y 6 letras es:', pal_4a6letras)
    print('La cantidad de palabras que contienen mas de 6 letras es:', pal_mas6letras)
    print('La cantidad de palabras con la expresion \"de\" en la primera mitad es:', pal_demitad)


test()

```

### 2. Sólo menores que 7

Desarrollar un programa de Phyton que permita cargar por teclado un secuencia de números, uno por uno. Siempre se supone que el usuario cargará un 0(cero) para indicar el final del proceso de carga. El cero no debe considerarse un dato a procesar. El programa debe: 

a) Determinar el porcentaje que cantidad de números pares representa en la cantidad total de números ingresados.

b) Determinar cuántos de los números ingresados tenían su último dígito igual a 4 o igual a 5.

c) Determinar el menor de los números ingresados que sean divisibles por 3.

d) Determinar si la secuencia estaba formada sólo por números menores o iguales que 7.

```python
def calcular_procentaje(cantidad, total):
    porcentaje = 0
    if total > 0:
        porcentaje = cantidad * 100 / total
    return porcentaje


def es_multiplo(numero, divisor):
    resto = numero % divisor
    return resto == 0


def es_par(numero):
    return es_multiplo(numero, 2)


def test():
    # variables para el punto 1
    cant_pares = 0
    cant_numeros = 0

    # variables para el punto 2
    cant_numeros_punto2 = 0

    # variables para el punto 3
    menor = None

    # variables para el punto 4
    # se inicializa con True, suponiendo que se ingresa una secuencia de numeros menores o iguales a 7
    # si dentro del ciclo se encuentra un numero que no cumple se cambia a false
    secuencia_menor_igual7 = True

    print('Ingrese una secuencia de números, la misma termina con un 0 (cero) : ')
    numero = int(input('Ingrese un número (distinto de 0): '))
    while numero != 0:
        cant_numeros += 1

        # punto 1
        # pregunta si es par
        if es_par(numero):
            cant_pares += 1

        # punto 2
        digito = numero
        if numero > 10:
            digito = numero % 10

        if digito == 4 or digito == 5:
            cant_numeros_punto2 += 1

        # punto 3
        # si el numero leido es divisible por 3 realiza proceso de busqueda de menor o menor no esta inicializado
        if es_multiplo(numero, 3):
            if menor is None or numero < menor:
                menor = numero

        # punto 4
        # si encuentra algun valor mayor a 7 ya no cumple
        if numero > 7:
            secuencia_menor_igual7 = False

        numero = int(input('Ingrese un número (distinto de 0): '))

    # punto 1
    # calcula el porcentaje
    porcentaje = calcular_procentaje(cant_pares, cant_numeros)

    # punto 4
    if secuencia_menor_igual7:
        mensaje = 'La secuencia estaba formada sólo por números menores o iguales que 7'
    else:
        mensaje = 'La secuencia NO estaba formada sólo por números menores o iguales que 7'

    # mostrar resultados
    print('\n El porcentaje de números pares sobre la cantidad total de números ingresados: ', porcentaje)
    print('\n La cantidad de números ingresados que tiene su último dígito igual a 4 o igual a 5: ', cant_numeros_punto2)
    print('\n El menor de los números ingresados que son divisibles por 3: ', menor)
    print('\n ', mensaje)


test()
```

### 3. Solamente 'a'

Desarrollar un programa que permita ingresar por teclado, con palabras separadas por un espacio y terminado en punto. En base al texto ingresado, determinar:

a) Cuál es la longitud de la palabra más larga.

b) Cuántas palabras tienen la a como única vocal

c) Qué porcentaje representan las que sólo tienen la vocal a sobre el total de palabras.

---

*Ejemplo:* *"el agua clara salta por las piedras."*

*La longitud de la palabra más larga es 7 letras*

*Las palabras cuya única vocal es la a son: 3*

*El porcentaje de estas palabras sobre el total es 43 %*

```python
def calcular_porcentaje(cantidad, total):
    if total == 0:
        porcentaje = 0
    else:
        porcentaje = round(cantidad * 100 / total)
    return porcentaje


def es_vocal(letra):
    vocales = 'aeiou'
    return letra in vocales


def test():
    print('Análisis de Texto')
    print('*' * 80)

    # Inicialización
    letras_pal = 0
    palabras = 0
    tiene_a = False

    tiene_eiou = False
    palabras_soloa = 0

    # Carga de datos y proceso
    texto = input('Ingrese el texto a analizar, separando las palabras con un espacio y terminando con punto: ')

    for letra in texto:
        if letra == ' ' or letra == '.':
            # Contar palabras
            if letras_pal > 0:
                palabras += 1

            # Buscar mayor
            if palabras == 1:
                mayor = letras_pal
            elif letras_pal > mayor:
                mayor = letras_pal
            # Tiene sólo a?

            if tiene_a and not tiene_eiou:
                palabras_soloa += 1

            # Reiniciar los indicadores de palabra
            letras_pal = 0
            tiene_a = False
            tiene_eiou = False
        else:
            # Determinar longitud
            letras_pal += 1

            # Detectar sólo a
            if es_vocal(letra):
                if letra == 'a':
                    tiene_a = True
                else:
                    tiene_eiou = True

    # Resultados
    print('*' * 80)
    print('La longitud de la palabra más larga es', mayor, 'letras')
    print('Las palabras cuya única vocal es la a son:', palabras_soloa)
    porcentaje = calcular_porcentaje(palabras_soloa, palabras)
    print('El porcentaje de estas palabras sobre el total es', porcentaje, '%')


# Script principal
test()

```

### 4. La letra T y los porcentajes

Desarrollar un programa en Python que permita cargar por teclado un texto completo. Siempre se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar la cantidad de palabras en las que solo aparece una única vez la letra “t”

b) Determinar la cantidad de palabras cuya cantidad de letras es mayor a la cantidad de letras de la palabra anterior

c) Determinar la cantidad de palabras con la cantidad de letras pares y comienzan con la letra “c”

d) Determinar el porcentaje que representa el primer punto sobre el total de las palabras del texto procesado

```python
def calcular_porcentaje(cantidad, total):
    porc = 0
    if total >= 0:
        porc = cantidad * 100 / total
    return round(porc, 2)


def es_par(numero):
    resto = numero % 2
    return resto == 0


def test():
    cantidad_t = pal_unica_t = cant_letra = letras_pal_ant = cant_palabras = pal_mayor_anterior = pal_pares_con_c = 0
    empieza_c = False

    print('La Letra T - Procesamiento de Texto')
    print('=' * 80)

    texto = input('Ingrese el texto a procesar, finaliza con un punto:')

    for caracter in texto:
        if caracter != ' ' and caracter != '.':
            cant_letra += 1

            if caracter == 't':
                cantidad_t += 1

            if cant_letra == 1 and caracter == 'c':
                empieza_c = True

        else:
            if cant_letra > 0:

                cant_palabras += 1

                if cantidad_t == 1:
                    pal_unica_t += 1

                if cant_palabras == 1:
                    letras_pal_ant = cant_letra
                else:
                    if cant_letra > letras_pal_ant:
                        pal_mayor_anterior += 1
                    letras_pal_ant = cant_letra

                if empieza_c and es_par(cant_letra):
                    pal_pares_con_c += 1

            cant_letra = 0
            cantidad_t = 0
            empieza_c = False

    porcentaje = calcular_porcentaje(pal_unica_t, cant_palabras)

    print('Resultados')
    print('=' * 80)
    print('La cantidad de palabras con una sola t son:', pal_unica_t)
    print('y representan el ', porcentaje, '% del total de palabras del texto', sep='')
    print('La cantidad de palabras con cantidad pares de letras y empiezan con c son:', pal_pares_con_c)
    print('La cantidad de palabras que tienen mas letras que la anterior son:', pal_mayor_anterior)


test()

```

### 5. Con m y b

Desarrollar un programa que permita ingresar por teclado, con palabras separadas por un espacio y terminado en punto. En base al texto ingresado, determinar:

a) Cuántas palabras tienen una m y una b a partir de la tercer letra.

b) Cuántas palabras comienzan con la letra p seguida de cualquier vocal.

c) Cuántas palabras comienzan y terminan con el mismo carácter.

---

*Ejemplo: 'Mi amiga Ambar siempre piensa y cambia pronto.'*

---

*Palabras tienen una m y una b a partir de la tercer letra: 1*  
*Palabras que comienzan con la letra p seguida de cualquier vocal: 1*  
*Palabras que comienzan y terminan con el mismo carácter: 2*

```python
def es_vocal(letra):
    vocales = 'aeiou'
    return letra in vocales


def test():
    print('Análisis de Texto')
    print('*' * 80)

    # Inicialización
    letras_pal = palabras_bym = palabras_pvocal = palabras_iniciofin = 0
    tiene_b = tiene_m = tiene_p = tiene_pvocal = False
    primera = None
    ultima = None

    # Carga de datos y proceso
    texto = input('Ingrese el texto a analizar, separando las palabras con un espacio y terminando con punto: ')

    for letra in texto:
        if letra == ' ' or letra == '.':
            # Tiene m y b a partir de la tercer letra?
            if tiene_b and tiene_m:
                palabras_bym += 1

            # Empieza con p seguida de vocal?
            if tiene_pvocal:
                palabras_pvocal += 1

            # Empieza y termina con la misma letra?
            if primera == ultima:
                palabras_iniciofin += 1

            # Reiniciar los indicadores de palabra
            letras_pal = 0
            tiene_b = False
            tiene_m = False
            tiene_p = False
            tiene_pvocal = False
            primera = None
            ultima = None
            
        else:
            # Contar letras de la palabra
            letras_pal += 1
            # Identificar m y b a partir de la tercer letra
            if letras_pal >= 3:
                if letra == 'b':
                    tiene_b = True
                elif letra == 'm':
                    tiene_m = True

            # Detectar si comienza con p seguida de vocal
            if letras_pal == 1 and letra == 'p':
                tiene_p = True

            if letras_pal == 2 and es_vocal(letra) and tiene_p:
                tiene_pvocal = True

            # Guardar primera letra
            if letras_pal == 1:
                primera = letra
            ultima = letra

    # Resultados
    print('*' * 80)
    print('Palabras tienen una m y una b a partir de la tercer letra:', palabras_bym)
    print('Palabras que comienzan con la letra p seguida de cualquier vocal:', palabras_pvocal)
    print('Palabras que comienzan y terminan con el mismo carácter:', palabras_iniciofin)


# Script principal
test()
```

### 6. Las 2 vocales

Desarrollar un programa en Python que permita cargar por teclado un texto completo. Siempre se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe

a) Determinar la cantidad de palabras en la que aparecen 2 vocales distintas

b) Determinar la cantidad de palabras cuya cantidad de letras es múltiplo de la cantidad de letras de la palabra anterior

c) Determinar la cantidad de palabras cuya cantidad de letras es superior a un valor ingresado por el usuario (debe ser mayor a cero)

d) Determinar la cantidad de palabras en las que su longitud en letras superan el promedio de letras del texto

```python
def es_vocal(caracter):
    vocales = 'aeiouáéíóú'
    return caracter in vocales


def leer_numero():
    numero = 0
    while numero <= 0:
        numero = int(input('Ingrese un numero: '))
        if numero <= 0:
            print('Error!!! el numero debe ser mayor a cero')
    return numero


def palabras_superan_promedio(texto, prom):
    cant_palabras = cant_letras = 0
    for caracter in texto:
        if caracter != ' ' and caracter != '.':
            cant_letras += 1
        else:
            if cant_letras > prom:
                cant_palabras += 1
    return cant_palabras


def es_multiplo(numero, divisor):
    resto = numero % divisor
    return resto == 0


def test():
    print('Analizador de Texto las 2 vocales')
    print('*' * 60)

    numero = leer_numero()
    texto = input('Ingrese el texto a analizar, finaliza con punto: ')

    pal_2voc_dif = cant_palabras = cant_letras = cant_let_pal_ant = pal_mult_ant = pal_let_mayor_num = total_letras = 0
    pal_sup_promedio = 0
    es_pri_vocal = True
    hay_2_voc_dif = False
    pri_vocal = ''

    for letra in texto:
        if letra == ' ' or letra == '.':
            if cant_letras > 0:

                cant_palabras += 1

                if hay_2_voc_dif:
                    pal_2voc_dif += 1

                if cant_palabras == 1:
                    cant_let_pal_ant = cant_letras
                else:
                    if es_multiplo(cant_letras, cant_let_pal_ant):
                        pal_mult_ant += 1
                    cant_let_pal_ant = cant_letras

                if cant_letras > numero:
                    pal_let_mayor_num += 1

                total_letras += cant_letras

            es_pri_vocal = True
            hay_2_voc_dif = False
            pri_vocal = ''
            cant_letras = 0

        else:
            cant_letras += 1

            if es_vocal(letra):
                if es_pri_vocal:
                    pri_vocal = letra
                    es_pri_vocal = False
                else:
                    if es_vocal(letra) and letra != pri_vocal:
                        hay_2_voc_dif = True
                        pri_vocal = ''

    if cant_palabras > 0:
        prom = total_letras // cant_palabras
        pal_sup_promedio = palabras_superan_promedio(texto, prom)

    print('La cantidad de palabras con 2 vocales diferentes son:', pal_2voc_dif)
    print('La cantidad de palabras cuya cantidad de letras es multiplo de la anterior son:', pal_mult_ant)
    print('Palabras que tienen mas de ', numero, 'letras son', pal_let_mayor_num)
    print('La cantidad de palabras que superan el promedio de letras de la palabra son', pal_sup_promedio)


test()
```

### 7. Dificultad = pow (parcial, 3)

Desarrollar un programa en Python que permita cargar por teclado un texto completo. Se supone que el usuario cargará un punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

a) Determinar la cantidad de palabras que tuvieron exactamente 3 vocales.

b) Determinar el porcentaje de palabras que tuvieron algún dígito ('0' al '9') y más de 4 letras.

c) De las palabras que terminan con la primera letra de todo el texto, determinar el **orden** de la que tiene menor cantidad de caracteres. Por ejemplo, en el texto: 'Ana está en la casa', hay 4 palabras que terminan en la primera letra del texto ('Ana', 'está', 'la', 'casa'), la que menos caracteres tiene es: 'la' y su orden es 4 (porque es la cuarta palabra del texto). 

d) Determinar la cantidad de palabras que contienen 'men' en la primera mitad de la palabra.

```python
def es_vocal(letra):
    vocales = 'aeiou'
    return letra in vocales


def es_digito(letra):
    digitos = '1234567890'
    return  letra in digitos


def calcular_porcentaje(cantidad, total):
    porcentaje = 0
    if total > 0:
        porcentaje = cantidad / total
    return round(porcentaje, 2)


def test():
    print('Analisis de Texto - vocales y digitos')
    print('=' * 80)

    texto = input('Ingrese el texto a analizar, temina con punto: ')
    cant_vocales = pal_3vocales = cant_palabras = pal_con_digitos = cant_letras = posicion = pal_men_pri_mitad = 0
    orden = 0
    tiene_digito = tiene_m = tiene_me = tiene_men = False
    menor = None
    for letra in texto:
        if letra == ' ' or letra == '.':
            cant_palabras += 1
            if cant_vocales == 3:
                pal_3vocales += 1

            if tiene_digito and cant_letras > 4:
                pal_con_digitos += 1

            mitad = cant_letras // 2
            if tiene_men and posicion <= mitad:
                pal_men_pri_mitad += 1
            
            if menor is None or cant_letras < menor:
                menor = cant_letras
                orden = cant_palabras
            
            cant_letras = 0
            tiene_men = tiene_m = tiene_me = False
        else:

            cant_letras += 1
            if es_vocal(letra):
                cant_vocales += 1

            if es_digito(letra):
                tiene_digito = True

            if letra == 'm' and not tiene_men:
                tiene_m = True
            else:
                if letra == 'e' and tiene_m:
                    tiene_me = True
                else:
                    if letra == 'n' and tiene_me:
                        tiene_men = True
                        posicion = cant_letras
                    tiene_me = False
                tiene_m = False

    porcentaje = calcular_porcentaje(pal_con_digitos, cant_palabras)
    print('La cantidad de palabras con exactamente 3 vocales es:', pal_3vocales)
    print('El porcentaje de palabras con digitos y mas de cuatro letras es: ', porcentaje, '%', sep='')
    print('La cantidad de palabras que tienen \"men\" en la primera mitad de la palabra es:', pal_men_pri_mitad)
    print('El orden de la menor palabra del texto es:', orden)


test()
```

```python
def calcular_porcentaje(muestras, total):
    """
    Calcula el porcentaje que representan las muestras en el total
    :param muestras: La cuenta de muestras
    :param total: El total sobre el que se contaron las muestras
    :return: El porcentaje que representan las muestras en el total si total es distinto a 0.
    0 en caso contrario
    """
    porcentaje = 0
    if total != 0:
        porcentaje = (muestras * 100) / total
    return porcentaje


def es_vocal(caracter):
    """
    Comprueba si un caracter es una vocal o no
    :param caracter: El caracter que se quiere comprobar
    :return: True si es una vocal, False si no lo es
    """
    vocales = 'aeiouáéíóú'  # Vocales (en minúsculas)
    for vocal in vocales:
        if caracter == vocal:
            return True

    return False


def es_digito(caracter):
    """
    Comprueba si un caracter es un dígito o no
    :param caracter: El caracter a comprobar
    :return: True si es un dígito, False en caso contrario
    """
    if caracter >= '0' and caracter <= '9':
        return True
    return False


def main():
    """
    Función principal del programa. Toda la lógica del mismo está contemplada aquí
    :return: None
    """
    ####################################################################################################################
    # Variables Generales (Variables que no se van a reiniciar, son los resultados del programa)                       #
    ####################################################################################################################
    cont_palabras = 0  # Contador de palabras del texto
    # Punto 1
    cont_punto_1 = 0  # Contador de Palabras con 3 vocales
    # Punto 2
    cont_punto_2 = 0  # Contador de palabras con dígitos y más de 4 caracteres
    # Punto 3
    cant_caracteres_menor = None  # Cantidad de carac. de la menor palabra que termina con la primera letra del texto
    pos_menor_palabra = None  # Posición de la palabra con menos carc. entre las que termina con la primera letra
    # Punto 4
    cont_punto_4 = 0  # Contador de palabras que contienen 'men' en la primera mitad de la palabra

    ####################################################################################################################
    # Variables por palabra (Variables que tienen sentido palabra por palabra, se reinician ante un serparador)        #
    ####################################################################################################################
    cont_letras_palabra = 0  # Contador de letras de la palabra que se está analizando
    # Punto 1
    cont_vocales_palabra = 0  # Contador de vocales de la palabra que se está analizando
    # Punto 2
    b_tiene_digito = False  # Bandera que indica si una palabra tiene o no un dígito entre sus caracteres
    # Punto 4
    b_m = b_me = False      # Banderas que indican si se vió una 'm' o si se vió 'me'
    b_tiene_men = False     # Bandera que indica si se encontró 'men' en la palabra
    pos_silaba_men = 0      # Posición en la que termina la sílaba 'men' si se la encontró en la palabra

    # Carga del texto
    texto = input('Ingrese texto: (Terminar con "."): ')
    # Conversión a minúsculas (Notar que esto no sirve si el enunciado solicita discriminar mayúsculas y minúsculas)
    texto = texto.lower()

    # Recorrido de la cadena
    for car in texto:

        if car != ' ' and car != '.':
            # De este lado, estamos dentro de una palabra
            cont_letras_palabra += 1

            # Para el punto 1 -> Contar vocales
            if es_vocal(car):
                cont_vocales_palabra += 1
            else:
                # Para el punto 2 -> ver si es un dígito. Notar que esto está en el else.
                # Esto es así, porque si es una vocal, no va a ser un dígito...
                if es_digito(car):
                    b_tiene_digito = True

            # Para el punto 3 -> determinar la primera letra del el texto. Para que se la primera
            # letra del texto, debe ser la primera palabra y el primer caracter de esa palabra.
            if cont_palabras == 0 and cont_letras_palabra == 1:
                primera_letra = car

            # Para el punto 4 -> Determinar si se encuentra 'men' y en qué posición de la palabra
            if car == 'm' and not b_tiene_men:
                # Si se encuentra una 'm' y todavía no se encontró 'men' en la palabra...
                b_m = True
            else:
                # Si se trata de una 'e' y en el caracter anterior se vió una 'm'
                if car == 'e' and b_m:
                    # Si entramos aquí, ya vimos 'me'
                    b_me = True
                else:
                    # Si vemos 'n' y teníamos 'me'
                    if car == 'n' and b_me:
                        # Entonces, vimos 'men'
                        b_tiene_men = True
                        # Pero también nos interesa la posición donde determinamos que vimos 'men'
                        pos_silaba_men = cont_letras_palabra
                    # Se baja la bandera b_me, para evitar que quede levantada si hemos visto 'me'
                    # pero no 'men'
                    b_me = False
                # Se baja la bandera b_m. Esto es para evitar que quede levantada la bandera cuando
                # no se vió 'me'
                b_m = False

            # Para el punto 3 -> se almacena el último caracter, para saber con qué termina la palabra.
            # Se hace al final del if por una cuestión de orden, en este caso pudo estar antes
            ultimo_car = car

        else:
            # En esta rama, estamos ante la posible terminación de una palabra
            if cont_letras_palabra > 0:
                # Únicamente se cuenta una palabra (y se la procesa) si consta de más de un caracter
                cont_palabras += 1

                # Para el punto 1 -> Si tiene exactamente 3 vocales, se la cuenta
                if cont_vocales_palabra == 3:
                    cont_punto_1 += 1

                # Para el punto 2 -> Si tiene un dígito y más de 4 letras
                if b_tiene_digito and cont_letras_palabra > 4:
                    cont_punto_2 += 1

                # Para el punto 3 -> Si termina con la primera letra del texto
                if ultimo_car == primera_letra:
                    # Pero como piden saber, dentro de todas las palabras que terminan con la primera letra
                    # del texto, cuál es la posición de la de menor cantidad de caracteres...
                    if cant_caracteres_menor is None or cont_letras_palabra < cant_caracteres_menor:
                        # Como en cualquier búsqueda de menor, nos quedamos con la cantidad de caracteres
                        # y la posición de la palabra (que es lo que nos piden)
                        cant_caracteres_menor = cont_letras_palabra
                        pos_menor_palabra = cont_palabras

                # Para el punto 4 -> Si contiene 'men' en la primera mitad de la palabra
                if b_tiene_men and pos_silaba_men <= (cont_letras_palabra / 2):
                    cont_punto_4 += 1

            # Reseteo de las variables que tienen que ver con cada palabra
            cont_letras_palabra = 0
            cont_vocales_palabra = 0
            b_tiene_digito = False
            pos_silaba_men = 0
            b_tiene_men = False

    # Terminó el for, aquí se procesan los resultados
    porc_punto_2 = calcular_porcentaje(cont_punto_2, cont_palabras)
    print('=============================== RESULTADOS ==============================')
    print('Total de palabras procesadas: ', cont_palabras)
    print('1) Cantidad de palabras con 3 vocales: ', cont_punto_1)
    print('2) Procentaje de palabras con algún dígito y más de 4 letras: ', round(porc_punto_2, 2))
    if pos_menor_palabra is not None:
        print('3) Posición de la menor palabra que termina con la primera letra del texto: ', pos_menor_palabra)
    else:
        print('3) No hubo palabras que terminasen con la primera letra del texto')
    print('4) La cantidad de palabras que contienen "men" en la primera mitad de la palabra es: ', cont_punto_4)


if __name__ == '__main__':
    main()
```

### 8. Entidad Bancaria

Una entidad bancaria necesita hacer una evaluación sobre las operatorias que han realizado sus clientes, para ello pide un programa que permita determinar dichas estadísticas.

Para ejecutarse correctamente el programa debe validar un token que cumple con las siguientes características:

  - Debe contener dos letras mayúsculas

  - Debe contener al menos 2 dígitos

  - Debe incluir el signo numeral en la segunda mitad del token

Si cumple el programa deberá pedir la cantidad de operaciones bancarias a procesar, ingresando en forma aleatoria para cada una de ellas:

  - Si fue una empresa o un particular

  - El monto que se opero

  - Si opera en pesos o en dólares

Luego presentar un menú de opciones que permita informar:

1 - Cantidad operaciones que se llevaron a cabo

2 - Porcentaje de operaciones en dólares

3 - Monto total operado en pesos por particulares

4 - Monto promedio operado en pesos por las empresas

```python
import random


def es_mayuscula(letra):
    return letra >= 'A' and letra <= 'Z'


def es_digito(car):
    digitos = '0123456789'
    return car in digitos


def validar_token(token):
    cant_may = 0
    cant_dig = 0
    pos = 0
    pos_numeral = 0
    for car in token:
        if es_mayuscula(car):
            cant_may += 1
        elif es_digito(car):
            cant_dig += 1
        elif car == '#':
            pos_numeral = pos
        pos += 1
    if cant_may == 2 and cant_dig >= 2 and pos_numeral > len(token) // 2:
        return True
    else:
        return False


def validar_positivo(mensaje):
    num = int(input(mensaje))
    while num <= 0:
        print('Inválido! Debe ser un valor mayor que cero')
        num = int(input(mensaje))
    return num


def generar_datos():
    tipos = 'Particular', 'Empresa'
    monedas = 'Pesos', 'Dolares'
    tipo = random.choice(tipos)
    monto = round(random.uniform(100, 100000), 2)
    moneda = random.choice(monedas)
    return tipo, monto, moneda


def calcular_porcentaje(cant, total):
    if total != 0:
        return cant * 100 / total
    else:
        return 0


def calcular_promedio(suma, cant):
    if cant != 0:
        return suma / cant
    else:
        return 0


def mostrar_menu(n, monto_particulares, porc_dolares, prom_empresas):
    opcion = -1
    while opcion != 0:
        print('-' * 60)
        print('Menu de Opciones')
        print('1 - Cantidad de operaciones')
        print('2 - Porcentaje de operaciones en dolares')
        print('3 - Monto total operado en pesos por particulares')
        print('4 - Monto promedio operado por empresas')
        print('0 - Salir')
        opcion = int(input('Ingrese su opcion: '))
        if opcion == 1:
            print('Total de operaciones =', n)
        elif opcion == 2:
            print('Porcentaje de operaciones en dolares =', round(porc_dolares, 2))
        elif opcion == 3:
            print('Monto total operado en pesos por particulares =', round(monto_particulares, 2))
        elif opcion == 4:
            print('Monto promedio operado en pesos por empresas =', round(prom_empresas, 2))
        print('-' * 60)


def principal():
    print('=' * 20, 'OPERACIONES BANCARIAS', '=' * 20)
    # SUB1 : Validar token
    token = input('Ingrese su token: ')
    if validar_token(token):
        # SUB2: Procesar operaciones
        n = validar_positivo('Ingrese cantidad de operaciones: ')
        ops_dolares = 0
        monto_particulares = 0
        monto_empresas = 0
        ops_empresas = 0
        for i in range(n):
            # Generar datos
            tipo, monto, moneda = generar_datos()
            print('Cliente', tipo, ' - Monto', monto, 'en', moneda)
            # Procesar
            if moneda == 'Dolares':
                ops_dolares += 1
            if moneda == 'Pesos':
                if tipo == 'Particular':
                    monto_particulares += monto
                elif tipo == 'Empresa':
                    monto_empresas += monto
                    ops_empresas += 1
        # Resultados
        porc_dolares = calcular_porcentaje(ops_dolares, n)
        prom_empresas = calcular_promedio(monto_empresas, ops_empresas)
        # SUB3: MOSTRAR MENU
        mostrar_menu(n, monto_particulares, porc_dolares, prom_empresas)
    else:
        print('El token ya no es valido')


principal()
```

## Ficha 11: Módulos y paquetes

### 1. Problema 1

Se solicita procesar un texto caracter a caracter. Las palabras del texto se separan con espacios en blanco y el fin del texto se indica con un punto.

A partir del texto se pide:

a. Determinar la cantidad de palabras que comienzan con la expresión ´SI´.

b. Determinar la cantidad de palabras que terminan con vocal y tienen una cantidad impar de letras.

c. Determinar la cantidad de palabras que tienen sólo una vocal.

d. Determinar la cantidad de palabras que comienzan y terminan con la misma letra.

e. Determinar la cantidad de palabras que contienen la expresión ´CC´.

f.  Determinar el porcentaje que representan las palabras del punto b sobre el total de palabras.

g. Determinar la longitud de la palabra más corta.

h. Determinar el promedio de letras por palabra.

```python

# determina si car es una vocal en mayuscula...
def is_vocal(car):
    if car in 'AEIOU':
        return True

    return False


# calcula el porcentaje y el promedio...
def calcular(cp, cv, ac):
    pc = 0
    pm = 0
    if cp > 0:
        pc = cv * 100 / cp
        pm = ac / cp

    return pc, pm


# funcion principal del programa...
def test():
    print("PROCESADOR DE TEXTO\n")

    # inicializamos variables
    ss = ssi = scc = False
    cvocal = clet = cc = cpal = cif = 0
    csi = cvi = clv = ccc = acu = 0
    primera = ultima = None
    menor = 0

    # carga del texto y conversión a maysucula...
    texto = input("Ingrese el texto a procesar (finalice con un punto): ")
    texto = texto.upper()

    # procesamiento del texto...
    for car in texto:
        if car != " " and car != ".":
            clet += 1

            # detector SI
            if car == "S" and clet == 1:
              ss = True

            else:
                if car == 'I' and ss:
                    ssi = True
                ss = False

            # detector vocales
            if is_vocal(car):
                cvocal += 1

            # inicio - fin
            if clet == 1:
                primera = car

            ultima = car

            # detector cc
            if car == "C":
                cc += 1
                if cc == 2:
                    scc = True

            else:
                cc = 0

        # fin de palabra
        else:
            if clet > 0:
                cpal += 1

                if cpal == 1:
                    menor = clet

                elif clet < menor:
                    menor = clet

                if ssi:
                    csi += 1

                if cvocal == 1:
                    clv += 1

                if is_vocal(ultima) and clet % 2 == 1:
                    cvi += 1

                if scc:
                    ccc += 1

                acu += clet

                if primera == ultima:
                    cif += 1

                clet = cc = cvocal = 0
                ss = ssi = scc = False

    # calculamos promedios y porcentajes
    porc, prom = calcular(cpal, cvi, acu)

    # visualización de resultados...
    print("Cantidad de palabras que comienzan con la expresión \"SI\":", csi)
    print("Cantidad que termina en vocal y con cantidad impar de letras:", cvi)
    print("Cantidad con una única vocal:", clv)
    print("Cantidad que comienza y termina con la misma letra:", cif)
    print("Cantidad que contiene la expresión \"CC\":", ccc)
    print("Porcentaje terminada en vocal y total impar de letras:", porc, "%")
    print("Longitud de la palabra más corta:", menor)
    print("Promedio de letras por palabra:", prom)


# script principal...
test()
```

```python
# SOLUCIÓN 2
def es_letra(car):
    if car != ' ' and car == '.':
        return True
    else:
        return False


def es_vocal(car):
    if car in "aeiou":
        return True
    else:
        return False


def es_impar(nro):
    if nro % 2 == 1:
        return True
    else:
        return False


def porcentaje(cantidad, total):
    return cantidad / total * 100


def promedio(suma, cantidad):
    if cantidad > 0:
        return suma / cantidad
    else:
        return 0


c_vocales = 0
c_letras = 0
c_palabras = 0
c_palabras_si = 0  # Cantidad de palabras con SI
c_palabras_cc = 0  # Cantidad de palabras con CC
c_palabras_vi = 0  # Cantidad de palabras con vocales impares
c_palabras_1v = 0  # Cantidad de palabras con una sola vocal
c_palabras_pu = 0  # Cantidad de palabras con primera y última letras iguales
minima = 0  # Longitud de palabra mínima
primera = None  # Primera letra de cada palabra
ultima = None  # Ultima letra de cada palabra
paso_s = False
paso_si = False
paso_c = False
paso_cc = False
paso_vocal = False
acum_letras = 0

texto = input('Ingrese un texto:').lower()

for car in texto:  # Por cada car del texto
    if es_letra(car):  # Si car es una letra o sea que no es un separador
        # Dentro de la palabra:
        c_letras += 1

        # Secuencia de dos letras diferentes
        if car == 's' and c_letras == 1:
            paso_s = True
        else:
            if car == 'i' and paso_s:
                paso_si = True
            paso_s = False

        # Secuencia de dos letras iguales
        if car == 'c':
            if paso_c:
                paso_cc = True
            paso_c = True
        else:
            paso_c = False

        # Contador de vocales y bandera de vocal en la letra anterior
        if es_vocal(car):
            c_vocales += 1
            paso_vocal = True
        else:
            paso_vocal = False

        # Para guardar la primera letra
        if c_letras == 1:
            primera = car

        # Guardar la anterior
        ultima = car
    else:
        # fuera de la palabra:
        if c_letras > 0:

            c_palabras += 1
            if paso_si:
                c_palabras_si += 1

            if paso_cc:
                c_palabras_cc += 1

            if paso_vocal and es_impar(c_letras):
                c_palabras_vi += 1

            if c_vocales == 1:
                c_palabras_1v += 1

            if primera == ultima:  # La anterior al separador es la última
                c_palabras_pu += 1

            if c_palabras == 1 or c_letras < minima:
                minima = c_letras

            acum_letras += c_letras

            # Limpieza para la próxima palabra
            c_letras = c_vocales = 0
            paso_s = paso_si = pasoc = paso_cc = paso_vocal = False
            primera = ultima = None

# Al final del texto
porcentaje_punto_b = porcentaje(c_palabras_vi, c_palabras)
promedio_letras = promedio(acum_letras, c_palabras)

# Presentación de resultados
print("Cantidad de palabras que comienzan con la expresión ´SI´:", c_palabras_si)
print("Cantidad de palabras que terminan con vocal y tienen una cantidad impar de letras:", c_palabras_vi)
print("Cantidad de palabras que tienen sólo una vocal:", c_palabras_1v)
print("Cantidad de palabras que comienzan y terminan con la misma letra:", c_palabras_pu)
print("Cantidad de palabras que contienen la expresión ´CC´:", c_palabras_cc)
print("Porcentaje que representan las palabras del punto b sobre el total de palabras:", porcentaje_punto_b)
print("Longitud de la palabra más corta:", minima)
print("Promedio de letras por palabra:", promedio_letras)

```

### 2. Mayusculas

Desarrollar un programa que permita ingresar un texto por teclado, con palabras separadas por un espacio y terminado en punto. En base al texto ingresado, determinar:

- Cantidad de palabras que empiezan con mayúscula.
- Cantidad de números del 0 al 9 en todo el texto.
- Cantidad de palabras que tienen más de una e.
- Promedio de letras por palabra, para las palabras de longitud impar.

*Ejemplo: Me llamo Elena y naci el 10 de febrero de 1990.*

---

*Palabras que empiezan con mayúscula: 2*  
*Numeros del 0 al 9 en todo el texto: 6*  
*Palabras que tienen más de una e: 2*  
*Promedio de letras por palabra, para las palabras de longitud impar: 4.5*

```python
def calcular_promedio (suma, total):
    if total != 0:
        promedio = round(suma / total, 2)
    else:
        promedio = 0
    return promedio


def es_mayuscula(letra):
    if letra >= 'A' and letra <= 'Z':
        return True
    else:
        return False


def es_numero(letra):
    numeros = '0123456789'
    if letra in numeros:
        return True
    else:
        return False


def test():
    print('Análisis de Texto')
    print('*' * 80)

    #Inicialización
    letras_pal = 0
    palabras_mayusc = 0
    cant_numeros = 0
    cant_e = 0
    palabras_e = 0
    palabras_impar = 0
    letras_impar = 0

    #Carga de datos y proceso
    texto = input('Ingrese el texto a analizar, separando las palabras con un espacio y terminando con punto: ')

    for letra in texto:
        if letra==' ' or letra=='.':
            #Tiene más de una e?
            if cant_e > 1:
                palabras_e += 1
            #Longitud impar? Acumular letras y contar
            if letras_pal % 2 != 0:
                palabras_impar += 1
                letras_impar += letras_pal
            #Reiniciar los indicadores de palabra
            letras_pal = 0
            cant_e = 0
        else:
            #Contar letras de la palabra
            letras_pal += 1
            #Empieza con mayúscula?
            if letras_pal==1 and es_mayuscula(letra):
                palabras_mayusc += 1
            #Contar si es un número
            if es_numero(letra):
                cant_numeros += 1
            #Contar letras e
            if letra == 'e' or letra == 'E':
                cant_e += 1
    #Resultados
    print('*' * 80)
    print('Palabras que empiezan con mayúscula:',palabras_mayusc)
    print('Numeros del 0 al 9 en todo el texto:',cant_numeros)
    print('Palabras que tienen más de una e:',palabras_e)
    promedio = calcular_promedio(letras_impar,palabras_impar)
    print('Promedio de letras por palabra, para las palabras de longitud impar:',promedio)

# Script principal
test()
```

### 3. Ejercicio lalelilolu

Escribir un programa guiado por menú de opciones que permita cargar un texto por teclado, el texto termina con '.' y las palabras se separan por espacios.

Luego a partir del texto cargado informar:

1. Promedio general de letras por palabra del texto.
2. Cantidad de palabras terminadas en vocal
3. Orden de la palabra más larga del texto.
4. Cantidad de palabras que contengan al menos una vez la sílaba l+vocal (es decir la, le, li, lo o lu
5. Cantidad de palabras que incluyan algún dígito en la primera mitad.
6. Cantidad de palabras que en su primera mitad incluyan dígitos tales que sumados individualmente dé por resultado un valor mayor o igual que 10.

```python
def es_vocal(letra):
    vocales = ('a', 'e', 'i', 'o', 'u')
    return letra in vocales

def leer_texto():
    texto = input('Ingrese el texto (termina con "." y las plabras se separan por espacio)\n')
    while(texto[-1] != '.'):
        print('Error: el texto debe terminar con "."')
        texto = input('Ingrese el texto (termina con "." y las plabras se separan por espacio)\n')
    texto = texto.lower()
    return texto

def leer_entero_en_rango(lim_inferior, lim_superior, mensaje):
    resp = int(input(mensaje))
    while(resp < lim_inferior or resp > lim_superior):
        print('Error: el numero debe estar entre ' + str(lim_inferior) + ' y ' + str(lim_superior) + ', vuelva a intentarlo.')
        resp = int(input(mensaje))

    return resp


def mostrar_menu():
    print('*' * 40)
    print('       Procesador de Textos')
    print('       Opciones:')
    print('*' * 40)
    print(' 1 - Cargar el Texto')
    print(' 2 - Mostrar el promedio de letras por palabra del texto')
    print(' 3 - Cantidad de palabras terminadas en vocal')
    print(' 4 - Orden de la palabra más larga')
    print(' 5 - Cantidad de palabras que contienen l + <vocal>')
    print(' 6 - Salir')


def pausa():
    input('\n\nPresione enter para continuar...\n')


def test():

    #Inicialización de contadores y acumuladores Generales
    texto_cargado = False
    acumulador_letras = 0
    contador_palabras = 0
    cont_pal_term_vocal = 0
    cont_pal_l_vocal = 0
    orden_mas_larga = 0
    letras_mas_larga = 0


    opcion = 0
    while (opcion != 6):
        mostrar_menu()
        opcion = leer_entero_en_rango(1, 6, 'Ingrese su opción: ')

        if (opcion == 1): # Cargar el texto

            # Inicializaciones
            contador_letras = 0
            ultima_letra = ' '
            vino_l = False
            vino_l_vocal = False

            texto = leer_texto()

            for car in texto:
                if (car != ' ' and car != '.'): # Por verdadero estoy procesando las letras dentro de una palabra
                    # Cuento las letras de la palabra
                    contador_letras += 1
                    # Me guardo cada letra para tener la última cuando la palabra termine
                    ultima_letra = car

                    # Detecto si vino l + vocal
                    if (car == 'l'):
                        vino_l = True
                    else:
                        if (vino_l and es_vocal(car)):
                            vino_l_vocal = True
                        vino_l = False
                else: # Por el falso esto al final de una palabra (o entre 2 palabras, parado en el espacio)
                    # Cuento las palabras
                    contador_palabras += 1

                    # Acumulo las letras para tener el total de letras para el promedio
                    acumulador_letras += contador_letras

                    # Cuentos las palabras con la última letra vocal
                    if (es_vocal(ultima_letra)):
                        cont_pal_term_vocal += 1

                    # Chequeo si la palabra anterior fue más larga y guardo los datos si asi fuera
                    if (contador_palabras == 1 or contador_letras > letras_mas_larga):
                        letras_mas_larga = contador_letras
                        orden_mas_larga = contador_palabras

                    #Cuento las palabras con l + vocal
                    if (vino_l_vocal):
                        cont_pal_l_vocal += 1

                    # Vuelvo al inicio los contadores y banderas para la próxima palabra
                    contador_letras = 0
                    vino_l = False
                    vino_l_vocal = False

            print('\n\nTexto procesado correctamente...\n\n')
            texto_cargado = True
            pausa()

        elif(opcion == 6): # Chau
            print('Gracias por usar el Procesador de Textos!!!')
            print('Fin!.')

        else:
            if (texto_cargado):
                if (opcion == 2): # Mostrar promedio
                    if (contador_palabras > 0):
                        promedio = acumulador_letras / contador_palabras
                    else:
                        promedio = 0
                    print('El promedio de letras por palabra fue:', promedio)
                    pausa()
                elif (opcion == 3): # Mostrar terminadas en vocal
                    print('La cantidad de palabras terminadas en vocal fue:', cont_pal_term_vocal)
                    pausa()
                elif (opcion == 4): # Mostrar terminadas en vocal
                    print('La ', orden_mas_larga, '° fue la palabra más larga, y tuvo ', letras_mas_larga, ' letras', sep='')
                    pausa()
                elif (opcion == 5): # Mostrar terminadas en vocal
                    print('La cantidad de palabras que incluyeron "l + <vocal>" fue:', cont_pal_l_vocal)
                    pausa()
            else:
                print('Debe cargar el texto primero ingresando a la opción 1')
                pausa()

test()
```

```python
# SOLUCIÓN SIN MENU
def es_vocal(letra):
    vocales = ('a', 'e', 'i', 'o', 'u')
    return letra in vocales

def leer_texto():
    texto = input('Ingrese el texto (termina con "." y las plabras se separan por espacio)\n')
    while(texto[-1] != '.'):
        print('Error: el texto debe terminar con "."')
        texto = input('Ingrese el texto (termina con "." y las plabras se separan por espacio)\n')
    texto = texto.lower()
    return texto

def pausa():
    input('\n\nPresione enter para continuar...\n')


def test():

    #Inicialización de contadores y acumuladores Generales
    texto_cargado = False
    acumulador_letras = 0
    contador_palabras = 0
    cont_pal_term_vocal = 0
    cont_pal_l_vocal = 0
    orden_mas_larga = 0
    letras_mas_larga = 0
    contador_letras = 0
    ultima_letra = ' '
    vino_l = False
    vino_l_vocal = False

    texto = leer_texto()

    for car in texto:
        if (car != ' ' and car != '.'): # Por verdadero estoy procesando las letras dentro de una palabra
            # Cuento las letras de la palabra
            contador_letras += 1

            # Detecto si vino l + vocal
            if (car == 'l'):
                vino_l = True
            else:
                if (vino_l and es_vocal(car)):
                    vino_l_vocal = True
                vino_l = False

            # Me guardo cada letra para tener la última cuando la palabra termine
            ultima_letra = car

        else: # Por el falso esto al final de una palabra (o entre 2 palabras, parado en el espacio)
            # Cuento las palabras
            contador_palabras += 1

            # Acumulo las letras para tener el total de letras para el promedio
            acumulador_letras += contador_letras

            # Cuentos las palabras con la última letra vocal
            if (es_vocal(ultima_letra)):
                cont_pal_term_vocal += 1

            # Chequeo si la palabra anterior fue más larga y guardo los datos si asi fuera
            if (contador_palabras == 1 or contador_letras > letras_mas_larga):
                letras_mas_larga = contador_letras
                orden_mas_larga = contador_palabras

            #Cuento las palabras con l + vocal
            if (vino_l_vocal):
                cont_pal_l_vocal += 1

            # Vuelvo al inicio los contadores y banderas para la próxima palabra
            contador_letras = 0
            vino_l = False
            vino_l_vocal = False

    print('\n\nTexto procesado correctamente...\n\n')
    texto_cargado = True
    pausa()

    # Mostrar promedio
    if (contador_palabras > 0):
        promedio = acumulador_letras / contador_palabras
    else:
        promedio = 0
    print('El promedio de letras por palabra fue:', promedio)
    pausa()
    # Mostrar terminadas en vocal
    print('La cantidad de palabras terminadas en vocal fue:', cont_pal_term_vocal)
    pausa()
    # Mostrar terminadas en vocal
    print('La ', orden_mas_larga, '° fue la palabra más larga, y tuvo ', letras_mas_larga, ' letras', sep='')
    pausa()
    # Mostrar terminadas en vocal
    print('La cantidad de palabras que incluyeron "l + <vocal>" fue:', cont_pal_l_vocal)
    pausa()


test()

```

### 4. Parcial 1 [1k01/05/14] 2017

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

1- Determinar la cantidad de palabras que terminaron en vocal. Por ejemplo, en el texto: “En el mar Dios me escucha.”, tiene 2 palabras terminadas en vocal.

2- El porcentaje de consonantes y el porcentaje de vocales en todo el texto (tener en cuenta que puede haber otros caracteres): “La universidad es una etapa mas de la vida entre los 18 y los 25 años.” Contiene 27 consonantes, 23 vocales y 54 caracteres en total.

3- Determinar qué palabra tuvo la mayor cantidad de consonantes del texto y mostrar su número de orden entendiendo que la primera palabra tiene orden 1. Por ejemplo, en el texto: “Los mandriles de Brasil son material de estudio.”, la palabra “mandriles” con 6 consonantes es la que más consonantes tiene y su número de orden es 2.

4- Determinar la cantidad de palabras que comenzaron con primera letra de todo el texto y además incluyeron “st”. Por ejemplo, en el texto: “En este parcial estamos evaluando lógica.”, encontramos 2 palabras que cumplen la condición “este” y “estamos”.

```python
def es_vocal(car):
    vocales = 'aeiouAEIOU'
    if car in vocales:
        return True
    else:
        return False


def es_consonante(car):
    consonantes = 'bcdfghjklmnñpqrstvwxyzBCDFGHJKLMNÑPQRSTVWXYZ'
    if car in consonantes:
        return True
    else:
        return False


def calcular_porcentaje(cant,total):
    if total == 0:
        return 0
    else:
        return cant * 100 / total
```

```python
def principal():
    #Inicialización
    anterior = ''
    pal_fin_vocal = letras = consonantes = vocales = palabras = cons_pal = letras_pal = pal_comienza_st = 0
    mayor = None
    comienza = tiene_st = False

    #Carga de datos y proceso
    texto = input('Ingrese el texto a analizar, separando las palabras con un espacio y terminando con punto: ')
    texto = texto.lower()
    for letra in texto:
        if letra != ' ' and letra != '.':
            #Dentro de la palabra
            letras_pal += 1
            if es_vocal(letra):
                vocales += 1
            elif es_consonante(letra):
                cons_pal += 1
            if palabras >= 1 and letras_pal == 1 and letra == texto[0]:
                comienza = True
            if letra == 't' and anterior == 's':
                tiene_st = True
        else:
            #Final de la palabra
            palabras += 1
            letras += letras_pal
            consonantes += cons_pal
            if es_vocal(anterior):
                pal_fin_vocal += 1
            if palabras == 1 or cons_pal > mayor[0]:
                mayor = cons_pal, palabras
            if comienza and tiene_st:
                pal_comienza_st += 1
            #Reiniciar
            cons_pal = 0
            letras_pal = 0
            comienza = False
            tiene_st = False
        anterior = letra

    #Resultados
    print('Palabras terminadas en vocal:',pal_fin_vocal)
    porc_voc = calcular_porcentaje(vocales,letras)
    porc_cons = calcular_porcentaje(consonantes,letras)
    print('Hay',round(porc_voc,2),'% de vocales y',round(porc_cons,2),'% de consonantes')
    print('La palabra con más consonantes tiene',mayor[0],'consonantes, y aparece en el orden',mayor[1])
    print('Palabras que comienzan con la primera letra del texto y contienen st:',pal_comienza_st)


if __name__ == '__main__':
    principal()
```

### 5. Parcial 1 [1k06] 2017

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

1. Determinar la cantidad de palabras que incluyeron al menos 2 dígitos, por ejemplo, el texto: “Argentina ganó 2 mundiales en 1978 y en 1986.” contiene 2 palabras con al menos 2 dígitos.
2. Determinar la cantidad de palabras que comienzan con “la”, por ejemplo, el texto: “Las laderas de las montañas están labradas.” contiene 4 palabras que comienzan con “la”.
3. Determinar el promedio de letras de las palabras que cumplieron con el punto 2, por ejemplo, en el texto anterior “laderas” y “labradas” cumplieron la condición y su promedio de letras por palabra fue 7.5.
4. Determinar la cantidad de palabras que comenzaron con “ll” y además incluyeron alguna “v”. Por ejemplo, en el texto: “Las lluvias se llevaron los llantos.”, contiene 2 palabras que cumplen la condición.

```python
def es_digito(letra):
    return letra in '0123456789'


def calcular_promerio(cantidad, total):
    prom = 0
    if total != 0:
        prom = round(cantidad / total, 2)
    return prom


def principal():
    texto = input('Ingrese el texto a procesar. Debe finalizar con punto: ')
    texto = texto.lower()
    cant_digitos = pal_digitos = pal_tiene_la = pal_ll_con_v = 0
    cont_letras = cont_letras_la = 0
    comienza_l = tiene_la = tiene_ll = tiene_v = False
    for letra in texto:
        if letra != ' ' and letra != '.':
            cont_letras += 1

            if es_digito(letra):
                cant_digitos += 1

            if cont_letras == 1 and letra == 'l':
                comienza_l = True
            else:
                if cont_letras == 2:
                    if comienza_l and letra == 'a':
                        tiene_la = True

                    if comienza_l and letra == 'l':
                        tiene_ll = True

                    comienza_l = False

            if letra == 'v':
                tiene_v = True

        else:
            if cant_digitos >= 2:
                pal_digitos += 1

            if tiene_la:
                pal_tiene_la += 1
                cont_letras_la += cont_letras

            if tiene_ll and tiene_v:
                pal_ll_con_v += 1

            cant_digitos = 0
            tiene_la = False
            tiene_ll = False
            tiene_v = False
            cont_letras = 0

    prom = calcular_promerio(cont_letras_la, pal_tiene_la)

    print('La cantidad de palabra con al menos 2 digitos son:', pal_digitos)
    print('La cantidad de palabras que comienzan con \"la\" son:', pal_tiene_la)
    print('El promedio de letras que comienzan con \"la\" es:', prom)
    print('La cantidad de palabras con \"ll\" con alguna \"v\" son


', pal_ll_con_v)


if __name__ == '__main__':
    principal()
```

### 6. Parcial 2 [1k03] 2018

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres.  

El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe:

1. Determinar cuántas palabras tenían más de cuatro letras y contenían al menos una "n". Por ejemplo, en el texto: “La universidad es una etapa más en el camino.”, hay 2 palabras que cumplen la condición ("universidad" y "camino"). 
  
2. Determinar el promedio de letras por palabra entre las que comenzaban con "t". Por ejemplo, en el texto: “Ahora tenemos otra tarea.”, hay 2 palabras que comienzan con "t" ("tenemos" y "tarea") y suman un total de 12 letras, por lo que el promedio pedido es p = 12 / 2= 6 letras por palabra. 
  

3. Determinar cuántas palabras contenían una "a" y también una "s", pero no contenían una "e". Por ejemplo, en el texto: "Ahora estamos en octavos de final del mundial.", hay una palabra que cumple la condición ("octavos"). La palabra "estamos" tiene una "a" y una "s", pero no cuenta porque tiene también una "e". 

4. Determinar cuántas palabras contenían al menos una vez la expresión "re" pero terminaban con la letra "o". Por ejemplo, en el texto: "El registro de goles ha revelado que el réferi se equivoca.". hay dos palabras que cumplen la condición ("registro" y "revelado"). La palabra "réferi" tiene la expresión "re", pero no cumple porque no termina en "o".

```python
def calcular_promedio(suma, cantidad):
    prom = 0
    if cantidad != 0:
        prom = round(suma / cantidad, 2)
    return prom


def principal():
    letras_pal = cp4ln = palabras_t = letras_palt = palabras_as = palabras_re = 0
    tiene_n = empieza_t = tiene_a = tiene_s = tiene_e = tiene_r = tiene_re = False
    ultima_letra = ''
    texto = input('Ingrese el texto, debe finalizar con punto: ')
    for letra in texto:
        if letra == ' ' or letra == '.':

            if letras_pal > 4 and tiene_n:
                cp4ln += 1

            if empieza_t:
                letras_palt += letras_pal
                palabras_t += 1

            if not tiene_e and tiene_a and tiene_s:
                palabras_as += 1

            if tiene_re and (ultima_letra == 'o' or ultima_letra == 'O'):
                palabras_re += 1

            letras_pal = 0
            tiene_n = empieza_t = tiene_a = tiene_s = tiene_e = tiene_r = False
        else:

            letras_pal += 1
            if letra == 'n' or letra == 'N':
                tiene_n = True

            if letras_pal == 1 and (letra == 't' or letra == 'T'):
                empieza_t = True

            if letra == 'a' or letra == 'A':
                tiene_a = True

            if letra == 's' or letra == 's':
                tiene_s = True

            if letra == 'e' or letra == 'E':
                tiene_e = True

            if letra == 'r' or letra == 'R':
                tiene_r = True
            else:
                if tiene_r and (letra == 'e' or letra == 'E'):
                    tiene_re = True
                tiene_r = False
            ultima_letra = letra

    print('La cantidad de palabras con mas de cuatro letras y '
          'contienen \"n\" son:', cp4ln)
    promedio = calcular_promedio(letras_palt, palabras_t)
    print('El promedio de letras por palabra entre las que '
          'comenzaban con \"t\" es', promedio)
    print('La cantidad palabras contenían una \"a\" y también una \"s\", pero no '
          'contenían una \"e\" son:', palabras_as)
    print('La cantidad palabras contenían  al menos una vez la expresión "re" pero'
          ' terminaban con la letra "o" son:', palabras_re)


if __name__ == '__main__':
    principal()
```

### 7. Parcial 2 [1k10] 2018

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco.

El programa debe:

1. Determinar cuántas palabras tenían por lo menos tres vocales y más de cuatro letras. Por ejemplo, en el texto: “La universidad es una etapa más de la vida.”, hay dos palabras que cumplen la condición ("universidad" y "etapa").
2. Determinar la longitud de la palabra más corta de entre las que contenían una consonante en la segunda posición. Por ejemplo, en el texto: "Vamos Argentina el sábado contra Francia", las palabras "Argentina", "el" y "Francia" tienen una consonante en la segunda letra, y la longitud de la más corta de esas tres palabras es 2 (corresponde a la palabra "el").
3. Determinar cuántas palabras empiezan con "v" o con "p" y terminan con "n" o con "a". Por ejemplo, en el texto: “Ahora que vengan y nos ganen si pueden.”, hay dos palabras que cumplen la condición ("vengan" y "pueden").
4. Determinar el porcentaje de palabras que contenían la expresión "ga" con respecto al total del palabras del texto. Por ejemplo, en el texto: “Ahora que vengan y nos ganen si pueden.”, hay 2 palabras con la expresión "ga" ("vengan" y "ganen") y hay un total de 8 palabras en todo el texto, por lo que el porcentaje pedido es pr = 2 * 100 / 8 = 25%

```python
def es_vocal(letra):
    vocales = 'aeiouAEIOU'
    if letra in vocales:
        return True
    else:
        return False


def es_letra(letra):
    if (letra >= 'a' and letra <= 'z') or (letra >= 'A' and letra <= 'Z'):
        return True
    else:
        return False


def es_consonante(letra):
    if es_letra(letra) and es_vocal(letra) == False:
        return True
    else:
        return False


def calcular_porcentaje(cantidad, total):
    if total != 0:
        porcentaje = cantidad * 100 / total
    else:
        porcentaje = 0
    return porcentaje


def principal():
    print('PROCESAMIENTO DE TEXTO')
    print('='*80)
    letras_pal = vocales_pal = 0
    segunda_consonante = empieza_vp = expresion_ga = False
    palabras_3voc4let = palabras_cons2 = menor_cons2 = palabras_vpna = palabras_ga = palabras = 0
    texto = input('Ingrese el texto, debe finalizar con punto: ')
    for letra in texto:
        if letra == ' ' or letra == '.':
            #Final de la palabra
            palabras += 1
            if vocales_pal >= 3 and letras_pal > 4:
                palabras_3voc4let += 1
            if segunda_consonante:
                palabras_cons2 += 1
                if palabras_cons2 == 1:
                    menor_cons2 = letras_pal
                elif letras_pal < menor_cons2:
                    menor_cons2 = letras_pal
            if empieza_vp and (anterior == 'n' or anterior == 'a'):
                palabras_vpna += 1
            if expresion_ga:
                palabras_ga += 1
            #Reiniciar variables de palabra
            segunda_consonante = empieza_vp = expresion_ga = False
            letras_pal = vocales_pal = 0
        else:
            #Dentro de la palabra
            letras_pal += 1
            if es_vocal(letra):
                vocales_pal += 1
            if letras_pal == 2 and es_consonante(letra):
                segunda_consonante = True
            if letras_pal == 1 and (letra == 'v' or letra == 'p'):
                empieza_vp = True
            if letra == 'a' and anterior == 'g':
                expresion_ga = True
        anterior = letra
    #Resultados
    print('=' * 80)
    print('Palabras que tenían por lo menos tres vocales y más de cuatro letras:',palabras_3voc4let)
    if palabras_cons2 > 0:
        print('Longitud de la palabra más corta de entre las que contenían una consonante en la segunda posición:',menor_cons2)
    else:
        print('No había palabras con una consonante en la segunda posición')
    print('Palabras que empiezan con "v" o con "p" y terminan con "n" o con "a":',palabras_vpna)
    porcentaje = calcular_porcentaje(palabras_ga,palabras)
    print('Porcentaje de palabras que contenían la expresión "ga":',round(porcentaje,2),'%')

if __name__ == '__main__':
    principal()
```

```python
def es_vocal(car):
    return car in 'aeiouAEIOUáéíóú'


def es_letra(car):
    if (car >= 'a' and car <= 'z') or (car >= 'A' and car <= 'Z'):
        return True
    else:
        return False


def es_consonante(car):
    if es_letra(car) and not es_vocal(car):
        return True
    else:
        return False


def calcular_porcentaje(cant, total):
    if total != 0:
        return cant * 100 / total
    else:
        return 0


def principal():
    texto = input('Ingrese texto: ')
    # Variables dentro de la palabra (debemos reiniciarlos al terminar la misma)
    letras_pal = vocales = 0
    tiene_cons2da = False
    empieza_vp = False
    tiene_ga = False
    # Variables para el texto (no se reinician)
    anterior = ''
    pals_3voc4let = 0
    men_cons2da = None
    pals_vp_na = 0
    pals_ga = 0
    palabras = 0
    for car in texto:
        if car != ' ' and car != '.':
            # Dentro de la palabra
            letras_pal += 1
            if es_vocal(car):
                vocales += 1
            if letras_pal == 2 and es_consonante(car):
                tiene_cons2da = True
            if letras_pal == 1 and (car == 'v' or car == 'p'):
                empieza_vp = True
            if anterior == 'g' and car == 'a':
                tiene_ga = True
        else:
            # Final de la palabra
            palabras += 1
            if vocales >= 3 and letras_pal > 4:
                pals_3voc4let += 1
            if tiene_cons2da:
                # Buscar palabra más corta
                if men_cons2da is None:
                    men_cons2da = letras_pal
                elif letras_pal < men_cons2da:
                    men_cons2da = letras_pal
            if empieza_vp and (anterior == 'n' or anterior == 'a'):
                pals_vp_na += 1
            if tiene_ga:
                pals_ga += 1
            # Reiniciamos variables de palabra
            letras_pal = vocales = 0
            tiene_cons2da = False
            empieza_vp = False
            tiene_ga = False
        anterior = car
    # La universidad es una etapa más de la vida.
    print('Palabras que tenían por lo menos tres vocales y más de cuatro letras:', pals_3voc4let)
    # Vamos Argentina el sabado contra Francia.
    if men_cons2da is None:
        print('No había palabras con una consonante en la segunda posición')
    else:
        print('Longitud de la palabra más corta de entre las que contenían una consonante en la segunda posición:',
              men_cons2da)
    # Ahora que vengan y nos ganen si pueden.
    print('Palabras empiezan con "v" o con "p" y terminan con "n" o con "a":', pals_vp_na)
    porcentaje = calcular_porcentaje(pals_ga, palabras)
    print('Porcentaje de palabras que contenían la expresión "ga" con respecto al total del palabras del texto:',
          round(porcentaje, 2), '%')


if __name__ == '__main__':
    principal()
```

### 8. Parcial 2 [1k15 T2] 2020

Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe incluir al menos una función simple con parámetros y retorno de resultado, debe procesar el texto caracter a caracter (a razón de uno por vuelta de ciclo), y debe hacer lo siguiente sin usar un menú de opciones:

- Determinar el promedio de dígitos por palabra de las palabras formadas solo por dígitos que posee el texto. Por ejemplo, en el texto: “En el 2020 hubo 130 alumnos en el 1k02.” Resultado: 2 palabras cumplen con la condición: (“2020” y “130”) y tienen 7 dígitos  entre la dos. Por lo tanto su promedio de dígitos por palabra es 3.5.
- Determinar la cantidad de palabras que finalizan con un dígito y tienen al menos una letra. Por ejemplo, en el texto: “En el 2020 hubo 130 alumnos en el 1k05 y 1k09.” Resultado: 2 palabras cumplen con la condición (“1k05” y “1k09”).
- Determinar la longitud y el orden o posición de la palabra más corta del texto. Por ejemplo, para el texto: “Este cuatrimestre hubo 130 alumnos en el 1k02.” Como las palabras más cortas son “en” y “el” de ellas puedo mostrar el orden y la posición de cualquiera de las dos (NO HAY que mostrar la palabra propiamente dicha). Resultado: La longitud es 2 y (si se tomó la primera), la posición es 6.
- Determinar la cantidad de palabras que tienen las letras “ch” continuas pero comenzando esa secuencia a partir de la cuarta letra en adelante. Por ejemplo, en el texto: “El chancho cochino juega en la hamaca.” Resultado: 1 palabra cumple con la condición (“chancho”). La palabra "cochino“ no cumple, porque la secuencia "ch" comienza en la tercera letra.

```python
def es_digito(car):
    if car >= '0' and car <= '9':
        return True
    else:
        return False


def calcular_promedio(suma, cant):
    if cant == 0:
        return 0
    else:
        return suma / cant


def es_letra(car):
    if (car >= 'a' and car <= 'z') or (car >= 'A' and car <= 'Z'):
        return True
    else:
        return False


def principal():
    print('Parcial 2 [1k15 T2] 2020')
    texto = input('Ingrese texto: ')
    # Variables de palabra (reiniciar)
    solo_digitos = True
    long_pal = 0
    tiene_letras = False
    tiene_ch = False
    ultimo = ''
    # Variables de texto (NO reiniciar)
    suma_solo_digitos = 0
    palabras_solo_digitos = 0
    palabras_digito_letra = 0
    palabras = 0
    palabras_ch = 0
    for car in texto:
        if car == ' ' or car == '.':
            palabras += 1
            if solo_digitos:
                suma_solo_digitos += long_pal
                palabras_solo_digitos += 1
            if es_digito(ultimo) and tiene_letras:
                palabras_digito_letra += 1
            if palabras == 1:
                men_long, men_pos = long_pal, palabras
            elif long_pal < men_long:
                men_long, men_pos = long_pal, palabras
            if tiene_ch:
                palabras_ch += 1
            # Reiniciar datos de palabra
            solo_digitos = True
            long_pal = 0
            tiene_letras = False
            tiene_ch = False
        else:
            # Dentro de la palabra
            long_pal += 1
            if not es_digito(car):
                solo_digitos = False
            if es_letra(car):
                tiene_letras = True
            if long_pal > 4 and car == 'h' and ultimo == 'c':
                tiene_ch = True
            ultimo = car
    # Resultados
    promedio = calcular_promedio(suma_solo_digitos, palabras_solo_digitos)
    print('Promedio de dígitos por palabra, entre las formadas sólo por dígitos:', promedio)
    print('Cantidad de palabras que finalizan con un dígito y tienen al menos una letra:', palabras_digito_letra)
    print('La palabra más corta tiene', men_long, 'caracteres y ocupó la posición', men_pos)
    print('Palabras con "ch" a partir de la cuarta letra:', palabras_ch)


if __name__ == '__main__':
    principal()

```

```python
# SOLUCION 2
# Se pide desarrollar un programa en Python que permita cargar por teclado un texto completo en una variable de tipo cadena de caracteres. El texto finaliza con ‘.’ y se supone que el usuario cargará el punto para indicar el final del texto, y que cada palabra de ese texto está separada de las demás por un espacio en blanco. El programa debe incluir al menos una función simple con parámetros y retorno de resultado, debe procesar el texto caracter a caracter (a razón de uno por vuelta de ciclo), y debe hacer lo siguiente sin usar un menú de opciones:
# Determinar el promedio de dígitos por palabra de las palabras formadas solo por dígitos que posee el texto. Por ejemplo, en el texto: “En el 2020 hubo 130 alumnos en el 1k02.” Resultado: 2 palabras cumplen con la condición: (“2020” y “130”) y tienen 7 dígitos  entre la dos. Por lo tanto su promedio de dígitos por palabra es 3.5.
# Determinar la cantidad de palabras que finalizan con un dígito y tienen al menos una letra. Por ejemplo, en el texto: “En el 2020 hubo 130 alumnos en el 1k05 y 1k09.” Resultado: 2 palabras cumplen con la condición (“1k05” y “1k09”).
# Determinar la longitud y el orden o posición de la palabra más corta del texto. Por ejemplo, para el texto: “Este cuatrimestre hubo 130 alumnos en el 1k02.” Como las palabras más cortas son “en” y “el” de ellas puedo mostrar el orden y la posición de cualquiera de las dos (NO HAY que mostrar la palabra propiamente dicha). Resultado: La longitud es 2 y (si se tomó la primera), la posición es 6.
# Determinar la cantidad de palabras que tienen las letras “ch” continuas pero comenzando esa secuencia a partir de la cuarta letra en adelante. Por ejemplo, en el texto: “El chancho cochino juega en la hamaca.” Resultado: 1 palabra cumple con la condición (“chancho”). La palabra "cochino“ no cumple, porque la secuencia "ch" comienza en la tercera letra.

def es_digito(car):
    if car >= '0' and car <= '9':
        return True
    else:
        return False


def calcular_promedio(suma, cant):
    if cant == 0:
        return 0
    else:
        return suma / cant


def es_letra(car):
    if (car >= 'a' and car <= 'z') or (car >= 'A' and car <= 'Z'):
        return True
    else:
        return False


def principal():
    print('PARCIAL 2')
    # Datos
    texto = input('Ingrese texto: ')
    # Variables de palabra (se reinician al terminar cada palabra)
    long_pal = 0
    solo_digitos = True
    tiene_letras = False
    tiene_ch = False
    ultimo = ''
    # Variables de texto (NO se reinician)
    suma_solo_dig = 0
    palabras_solo_dig = 0
    palabras_dig_let = 0
    cant_palabras = 0
    palabras_ch = 0
    # Proceso
    for car in texto:
        if car == ' ' or car == '.':
            if long_pal > 0:
                cant_palabras += 1
            if solo_digitos:
                suma_solo_dig += long_pal
                palabras_solo_dig += 1
            print(ultimo)
            if es_digito(ultimo) and tiene_letras:
                palabras_dig_let += 1
            if cant_palabras == 1:
                men_long, men_pos = long_pal, cant_palabras
            elif long_pal < men_long:
                men_long, men_pos = long_pal, cant_palabras
            if tiene_ch:
                palabras_ch += 1
            # Reiniciar variables de palabra
            long_pal = 0
            solo_digitos = True
            tiene_letras = False
            tiene_ch = False
        else:
            # Dentro de la palabra
            long_pal += 1
            if es_digito(car) == False:
                solo_digitos = False
            if es_letra(car):
                tiene_letras = True
            if car == 'h' and ultimo == 'c' and long_pal > 4:
                tiene_ch = True
            ultimo = car
    # Resultados
    print('-' * 80)
    promedio = calcular_promedio(suma_solo_dig, palabras_solo_dig)
    print('Promedio de dígitos por palabra de las palabras formadas solo por dígitos:', promedio)
    print('Palabras que finalizan con un dígito y tienen al menos una letra:', palabras_dig_let)
    print('La menor longitud es', men_long, 'y apareció en el orden o posición', men_pos)
    print('Palabras que tienen “ch” comenzando esa secuencia a partir de la cuarta letra:', palabras_ch)


if __name__ == '__main__':
    principal()
```

### 9. Ejercicio Proceso de Cadenas.

Procesar un texto que se ingresa por teclado, en el texto las palabras están separadas por uno o más espacios en blanco y el texto finaliza con un ".".  
El programa debe estar organizado en funciones y el script principal solo puede contener una llamada a una función para iniciar el programa. El texto se debe procesar de a una letra por vez (es decir una letra por vuelta de ciclo). En base a los lineamientos anteriores el programa debe determinar:  
1 - Determinar el porcentaje de palabras con más vocales que consonantes.  
2 - Determinar la cantidad de caracteres de la palabra con menor cantidad de caracteres del texto.  
3 - Determinar cantidad de palabras que tuvieron al menos una vez la secuencia 'sa' o 'se' o 'si' o 'so' o 'su'.  
4 - Determinar la cantidad de palabras que comenzaron el último caracter de la palabra anterior.

```python
def es_vocal(car):
   # if car in 'aeiouáéíóú':
   #  return True
   # else:
   #  return False
   return car in 'aeiouáéíóú'
   # return car in ('a', 'e', 'i', 'o', 'u')


def es_consonante(car):
   return car in 'bcdfghjklmnpqrstvwxyz'


def inicio():

   print('Analizador de Texto')
   print('Ingrese el texto a analizar (finaliza con punto): ')
   cadena = input()
   cadena = cadena.lower()

   contador_palabras = 0
   contador_letras_palabra = 0
   # acumulador_letras = 0
   contador_vocales = 0
   contador_consonantes = 0
   contador_pal_punt0_1 = 0
   bandera_letra_s = bandera_letra_s_vocal = False
   contador_pal_punto_3 = 0
   bandera_comienza_ultima_letra = False
   contador_pal_punto_4 = 0
   ultima_letra = None

   for car in cadena:
      if car == '.' or car == ' ':
         # Fin de palabra

         # Control más de un espacio seguido
         if contador_letras_palabra == 0:
            continue

         contador_palabras += 1

         if contador_vocales > contador_consonantes:
            contador_pal_punt0_1 += 1

         if contador_palabras == 1 or contador_letras_palabra < menor:
            menor = contador_letras_palabra

         if bandera_letra_s_vocal:
            contador_pal_punto_3 += 1

         if bandera_comienza_ultima_letra:
            contador_pal_punto_4 += 1

         # Reinicialización de contadores y banderas de la palabra
         contador_letras_palabra = 0
         contador_vocales = contador_consonantes = 0
         bandera_letra_s = bandera_letra_s_vocal = False
         bandera_comienza_ultima_letra = False

         # Fin sector fin palabra
      else:
         # Dentro de Palabra
         contador_letras_palabra += 1
         if es_vocal(car):
            contador_vocales += 1
         else:
            if es_consonante(car):
               contador_consonantes += 1
         if car == 's':
            bandera_letra_s = True
         else:
            if bandera_letra_s and es_vocal(car):
               bandera_letra_s_vocal = True
            bandera_letra_s = False
         # Versión de condición sin necesidad de inicializar ultima_letra aportada por alumno.
         # if contador_palabras > 0 and contador_letras_palabra == 1 and car == ultima_letra:
         if contador_letras_palabra == 1 and car == ultima_letra:
            bandera_comienza_ultima_letra = True


         # Fin sector dentro de palabra

   print('\n\n Resultados')
   print('===========================>')
   if contador_palabras > 0:
      print('Cantidad de palabras:', contador_palabras)
      porcentaje = contador_pal_punt0_1 * 100 / contador_palabras
      print(f'Porcentaje punto 1: {porcentaje}%')
      print(f'La palabra con menos letras tuvo {menor} letras')
      print(f'La cantidad de palabras con s+vocal fue {contador_pal_punto_3}')
      print(f'La cantidad de palabras que comenzaron con la última letra de la palabra anterior fue {contador_pal_punto_4}')
   else:
      print('No cargó nada')


# Script Principal
inicio()
```
