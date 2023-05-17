# Programación de Computadores - UNAL
# Tuplas

<table cellspacing="1" bgcolor="">
	<tr bgcolor="#252582">
		<th><b>Definición</b></th>
	</tr>
	<tr bgcolor="#e4e4ed">
		<td style="color:#141414">Una tupla es una secuencia de elementos que puede almacenar datos heterogéneos tales como: enteros, reales, cadenas, listas, diccionarios y otros más, inclusive otras tuplas. Una tupla se escribe como la secuencia de datos a mantener, separados por una coma ( , ), secuencia delimitada por los paréntesis redondos. Como las cadenas de caracteres, las tuplas son <b>inmutables</b>, esto es, no se pueden modificar después de definidas.
	</tr>
</table>

**Ejemplos:**
 + ( ) : La tupla vacía.
 + ("Este es un texto",) : Una tupla con un elemento que es una cadena. Para el caso de tuplas de un sólo elemento Python requiere una coma final para considerarla una tupla.
 + ('Una cadena', 123) : Una tupla de dos elementos, el primero una cadena y el segundo un número entero.
 + (1, 2, 3, 4.5, 'hola', 'a') : Una tupla de seis elementos.

 ### Asignación
 Una tupla se puede asignar a una variable de dos maneras: Usando los paréntesis redondos o sólo la secuencia de datos separados por comas.
 + x = () : Le asigna la tupla vacía a la variable x.
 + tup = (1, 2, 3, 4.5, 'hola', 'a') : Le asigna la tupla de seis elementos a la variable tup. 
 + a = 1, 2, 3 : Le asigna la tupla (1, 2, 3) a la variable a.

**Ejemplo 1:**  Tuplas de tuplas.
```python
tuple1 = (0, 1, 2, 3)
tuple2 = ("A", "B", "C")
tuple3 = (tuple1, tuple2)
print(tuple3)
print(tuple3[0])
print(tuple3[1])
print(tuple3[1][0])
```

## Opeardores
### Concatenar
Concatena (pega) dos cadenas. Se utiliza el simbolo *+*.

**Ejemplo 2:** 
```python
tup1 = ("A", "B", "C", "E")
tup2 = (1, 2, 3, 4, 5)
tup3 = tup1 + tup2
print(tup3)
```

### Repetir
Crea una tupla con múltiples copias de una tupla, tantas como se defina.

**Ejemplo 3:** 
```python
tup2 = (1, 2, 3, 4, 5)
tup3 = tup2 * 3
print(tup3)
tup4 = ("Abc", "Bcd")
tup5 = tup4 * 2
print(tup5)
```

### Comparar
Se usan los operadores convencionales (<, <=, >, >=, ==, !=) para comparar tuplas usando el orden lexicográfico, cuando es posible. En el orden lexicográfico, se tratan de comparar (si el operador < está definido), de izquierda a derecha uno a uno los elementos de la tupla, mientras sean iguales. En el caso en el que no este definido el orden (por ejemplo entre cadenas y números), la comparación genera un error. En el caso que no sean iguales, si el elemento de la primera tupla es menor que el de la segunda, la primer tupla se considera la menor, si el elemento es mayor la primer tupla se considera la mayor. Si todos los elementos son iguales, se consideran iguales a las tuplas.

**Ejemplo 4:** 
```python
print(("Rojas", 123) < ("Rosas", 123))
print(("Rosas", 123) == ("rosas", 123))
print(("Rosas", 123) > ("Rosas", 23))
print(("Rojas", "123") > ("Rosas", 23))
print(("Rosas", "123") > ("Rosas", 23))
```

### Subíndice
Accede los elementos de una tupla. Si la posición que se envía es negativa, lo considera desde el final. Si no es válida genera error.

**Ejemplo 5:** 
```python
avengers = ("Ironman", "Thor", "Ant-man", "Hulk")
print(avengers[0])
print(avengers[3])
print(avengers[-1])
print(avengers[-3])
```

### Pertenencia
Es posible determinar si una subcadena se encuentra en una tupla. Se utiliza el operador *in*.

**Ejemplo 6:** 
```python
text = ("cien", "a~nos", "de", "soledad")
if "a~nos" in text:
print("Si está en la tupla")
else:
print("No está en la tupla"
```

Al igual que una lista, una tupla se puede convertir en un iterable utilizando el bucle *for* y el operador *in*.

**Ejemplo 7:** 
```python
s = ("hola", "amigos", "mios")
for palabra in s: # para cada palabra de la tupla
  print(palabra, end = ", ")
```

### Asignación múltiple
Es posible asignarle los valores a un grupo de variables usando la asignación y el concepto de tupla.

**Ejemplo 8:** 
```python
tupla = (1, -2, 3)
a, b, c = tupla
print("a =", a)
print("b =", b)
print("c =", c)
```

**Ejemplo 9:** 
```python
a = 1
b = 3
a, b = b, a
print("a =", a)
print("b =", b)
```

### Tuple comprehension
Es posible asignar los valores de un grupo de variables usando la asignación, el ciclo for y el concepto de tupla.

**Ejemplo 10:** 
```python
tupla = (11, 9, -2, 3, 8, 5)
var1, var2, var3 = (tupla[i] for i in (1, 3, 5))
print("var1 =", var1, ", var2 =", var2, ", var3 =", var3)
var1, var2, var3 = (tupla[i] for i in range(0,6,2))
print("var1 =", var1, ", var2 =", var2, ", var3 =", var3)
```

### Multiples returns
Retornar más de un valor en una función usando el concepto de tupla.

**Ejemplo 11:** 
```python
def minmax(a, b):
  if a < b:
    return a, b
  else:
    return b, a

if __name__ == "__name__":
  x, y = minmax(5, 13)
  print("min =", x, ",", "max =", y)
  x, y = minmax(12, -4)
  print("min =", x, ",", "max =", y)
```

## Métodos
### len()
La función len determina la dimensión (longitud) de una tupla.

**Ejemplo 12:** 
```python
tup = (1, 2, 3, 4)
nombre = ("Minch", "Yoda")
trabajo = ("Stars", "War", "Movie")
empty = ()
print(len(tup))
print(len(nombre))
print(len(trabajo))
print(len(empty))
```

### Slicing
La función slice obtiene una porción (subtupla) de una tupla. La definición es similar a la función slice, de cadena [inicio:fin:incremento].

**Ejemplo 13:** 
```python
avengers = ("Ironman", "Thor", "Ant-man", "Hulk")
print(avengers[:2])
print(avengers[1:3])
print(avengers[3:3])
print(avengers[::-1])
```

### Contar
El método count obtiene las veces que un elemento se encuentra en una tupla.

**Ejemplo 14:** 
```python
tupla = (4, 3, 8, 8, 2, 5, 4, 6, 8, 9)
print(tupla.count(2))
print(tupla.count(8))
print(tupla.count(5))
print(tupla.count(7))
```

### Busqueda 
El método index obtiene la primera ocurrencia de un elemento en una tupla.

**Ejemplo 15:** 
```python
tupla = (4, 3, 8, 8, 2, 5, 4, 6, 8, 9)
print(tupla.index(2))
print(tupla.index(8))
print(tupla.index(5))
```

### Maximo y minimo
El método max/min obtiene el máximo/mínimo elemento de una tupla.

**Ejemplo 15:** 
```python
t = (4, 5, -1, 6, 7)
print(max(t))
print(min(t))
```

### Conversion string a tupla
El método tuple se usa para crear tuplas a partir de otros objetos, aquí se usa para convertir una cadena de caracteres a tupla.

**Ejemplo 16:** 
```python
magician = "Dumbledore"
tm = tuple(magician)
print(tm)
```

### Unpacking
Una forma rápida de desempacar y asignar variables de una tupla.

**Ejemplo 17:** 
```python
tup1 = (1, 2, 3)
a, b, c = tup1
print("a:", a, "b:", b, "c:", c)
```