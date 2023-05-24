# las_matricces_y_yo-no_somos_compatibles
Reto #11, matrices y demás funciones:)
## Primer punto:
- Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
#### Explicación:
- Primero investigue como ingresar una matriz por teclado, la funsion toma como argumentos la cantidad de filas y columnas que ingrese el usuario alli se crea una lista vacia que se llamara matriz, cree un ciclo for que recorre el elemento i en la cantidad de filas, luego creamos una lista vacia llamada fila y ponemos un ciclo for para que recoorra en las columnas, luego creamos la variable elemento para que el usuario ingrese los elementos de la matriz segun la cantidad que haya puesto. Para sumar las matrices se crea una lista vacia llamada resultado luego con ciclos fpr aninados daremos el indice de colmna y fila de cada matriz las cuales proceden a sumar dichos indices y asi mismo se hace con la resta.
```
def ingresar_matriz(filas, columnas): 
     """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
     matriz = [] # se crea una lista vacia donde se almacenara la matriz
     for i in range(filas): #se crea un ciclo for para elemento i en el rango de filas
        fila = [] # se crea una lista con las filas
        for j in range(columnas): #se crea un ciclo for para el elemento j en el rango de columnas 
            elemento = int(input(f"Ingrese el elemento [{i}][{j}]: ")) # se solicita ingresar los elementos en este formato
            fila.append(elemento) #se agrega el elemento en filas
        matriz.append(fila)# se agrega a la matriz
     return matriz

def sumar_matrices(m1, m2):
    """
    Realiza la suma de dos matrices.

    Argumentos:
        matriz1(m1)-(list): La primera matriz.
        matriz2(m2)-(list): La segunda matriz.

    Returns:
        list: La matriz resultante de la suma.
    """
    resultado = [] # se crea una lista vacia para almacenar los resultados
    for i in range(len(m1)): # creamos un for para saber cual es la fila
        fila = []#una lista vacia donde se almacenara las filas
        for j in range(len(m1[0])): # itera de nuevo pero en las columnas
            fila.append(m1[i][j] + m2[i][j])# se suman segun sus pocisiones
        resultado.append(fila)# se agrega las suma a la lista de resultado
    return resultado


def restar_matrices(m1, m2):
    """
    Realiza la resta de dos matrices.

    Args:
        matriz1 (list): La primera matriz.
        matriz2 (list): La segunda matriz.

    Returns:
        list: La matriz resultante de la resta.
    """
    resultado = [] # lista vacia
    for i in range(len(m1)): # se realiza los mismo que en la suma 
        fila = []
        for j in range(len(m1[0])): # itera en las columnas
            fila.append(m1[i][j] - m2[i][j]) # se restan en estas pocisiones
        resultado.append(fila)
    return resultado

if __name__ == "__main__":
 # Solicitar al usuario las dimensiones de las matrices
 filas = int(input("Ingrese el número de filas de las matrices: "))
 columnas = int(input("Ingrese el número de columnas de las matrices: "))

 matriz1 = ingresar_matriz(filas, columnas)
 print("matriz 1:", matriz1)


 matriz2 = ingresar_matriz(filas, columnas)
 print("Matriz 2",matriz2)

# Verificar si las matrices tienen las mismas dimensiones
if len(matriz1) != len(matriz2) or len(matriz1[0]) != len(matriz2[0]):
    print("Error: Las matrices deben tener las mismas dimensiones para realizar la operación.")
else:
    # Realizar la suma y resta de las matrices
    matriz_suma = sumar_matrices(matriz1, matriz2)
    matriz_resta = restar_matrices(matriz1, matriz2)

    # Mostrar los resultados
    print("La suma de las matrices es:")
    for fila in matriz_suma:
        print(fila)

    print("La resta de las matrices es:")
    for fila in matriz_resta:
        print(fila)
```
## Punto 2:
- Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
#### Explicación: 
- Tenemos la función para ingresar matrices, luego Toma dos argumentos: matriz1 y matriz2, que son las matrices a multiplicar. La función crea una lista vacía llamada resultado donde se almacenará la matriz resultante. Luego, utiliza tres bucles for anidados para recorrer las filas y columnas de las matrices de entrada. En cada iteración, realiza el cálculo de la multiplicación de los elementos correspondientes de las matrices y los acumula en la variable elemento. Posteriormente, agrega elemento a la lista fila, y finalmente agrega la lista fila a la matriz resultado. Al finalizar, la función retorna la matriz resultante.
```
def ingresar_matriz(filas, columnas): 
     """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
     matriz = [] # se crea una lista vacia donde se almacenara la matriz
     for i in range(filas): #se crea un ciclo for para elemento i en el rango de filas
        fila = [] # se crea una lista con las filas
        for j in range(columnas): #se crea un ciclo for para el elemento j en el rango de columnas 
            elemento = int(input(f"Ingrese el elemento [{i}][{j}]: ")) # se solicita ingresar los elementos en este formato
            fila.append(elemento) #se agrega el elemento en filas
        matriz.append(fila)# se agrega a la matriz
     return matriz

def multiplicar_matrices(matriz1, matriz2):
    """
    Realiza el producto de dos matrices.

    Args:
        matriz1 (list): La primera matriz.
        matriz2 (list): La segunda matriz.

    Returns:
        list: La matriz resultante del producto.
    """
    resultado = [] # se crea una lista vacia donde se almacenara el resultado 
    for i in range(len(matriz1)): #se recorre las filas
        fila = []
        for j in range(len(matriz2[0])):# se recorren las columnas 
            elemento = 0 # se inicializa la variable elemento en 0
            for k in range(len(matriz2)): #se utiliza el elemento de la fila de la otra matriz
                elemento += matriz1[i][k] * matriz2[k][j] # a la variable elemento se le suma la multiplicacion de las siguientes pocisiones
            fila.append(elemento)# se agrega el cada elemento multiplicado a la lista
        resultado.append(fila) #estas se agrega a la lista de resultados 
    return resultado
if __name__ == "__main__":
 # Solicitar al usuario las dimensiones de las matrices
 filas = int(input("Ingrese el número de filas de las matrices: "))
 columnas = int(input("Ingrese el número de columnas de las matrices: "))

 matriz1 = ingresar_matriz(filas, columnas)
 print("matriz 1:", matriz1)


 matriz2 = ingresar_matriz(filas, columnas)
 print("Matriz 2",matriz2)

# Verificar si las matrices tienen las mismas dimensiones
if len(matriz1) != len(matriz2) or len(matriz1[0]) != len(matriz2[0]):
    print("Error: Las matrices deben tener las mismas dimensiones para realizar la operación.")
else:
    # Realizar la suma y resta de las matrices
    matriz_multiplicacion = multiplicar_matrices(matriz1, matriz2)
    

    # Mostrar los resultados
    print("el producto de las matrices es:")
    for fila in matriz_multiplicacion:
        print(fila)
```
## Punto 3:
- Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.
#### Explicación: 
- Esta función recibe una matriz como argumento y calcula su matriz transpuesta. Comienza obteniendo el número de filas y columnas de la matriz. Luego, crea una lista vacía llamada matriz_transpuesta, donde se almacenará la matriz transpuesta. Utiliza dos bucles for anidados para recorrer la matriz original. En cada iteración, accede al elemento matriz[i][j] de la matriz original y lo agrega a la lista fila_transpuesta, intercambiando la posición de los índices i y j. Después de recorrer todas las filas y columnas.
```
def ingresar_matriz(filas, columnas): 
     """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
     matriz = [] # se crea una lista vacia donde se almacenara la matriz
     for i in range(filas): #se crea un ciclo for para elemento i en el rango de filas
        fila = [] # se crea una lista con las filas
        for j in range(columnas): #se crea un ciclo for para el elemento j en el rango de columnas 
            elemento = int(input(f"Ingrese el elemento [{i}][{j}]: ")) # se solicita ingresar los elementos en este formato
            fila.append(elemento) #se agrega el elemento en filas
        matriz.append(fila)# se agrega a la matriz
     return matriz

def obtener_matriz_transpuesta(matriz):
    """
    Obtiene la matriz transpuesta.

    Argumento:
        matriz (list): La matriz.

    Returns:
        list: La matriz transpuesta.
    """
    filas = len(matriz) 
    columnas = len(matriz[0])

    matriz_transpuesta = [] # se crea una lista vacia
    for j in range(columnas):# para un elemento j en el rango de columnas
        fila_transpuesta = []# se da una lista vacia de la fila
        for i in range(filas):# para un elemento i en el rango de filas
            fila_transpuesta.append(matriz[i][j])# se agrega el elemento cambiando su posicion
        matriz_transpuesta.append(fila_transpuesta)

    return matriz_transpuesta

if __name__ == "__main__":
 filas = int(input("Ingrese el número de filas de la matriz: "))
 columnas = int(input("Ingrese el número de columnas de la matriz: "))


 matriz = ingresar_matriz(filas, columnas)
 for fila in matriz:
  print(fila)

 #  Obtener la matriz transpuesta
 matriz_transpuesta = obtener_matriz_transpuesta(matriz)

 # Mostrar el resultado
 print("La matriz transpuesta es:")
 for fila in matriz_transpuesta: # la matrzi queda en formato vertical
    print(fila)
```
## Punto 4:
- Desarrollar un programa que sume los elementos de una columna dada de una matriz.
#### Explicación:
- Esta función recibe una matriz y un índice de columna como argumentos y calcula la suma de los elementos de esa columna en particular. Comienza inicializando una variable suma en 0. Luego, utiliza un bucle for para recorrer cada fila de la matriz. Dentro del bucle, verifica si el índice de columna es válido para la fila actual. Si es así, suma el elemento correspondiente de la columna a la variable suma. Finalmente, retorna el valor de suma.
```
def ingresar_matriz(filas, columnas): 
     """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
     matriz = [] # se crea una lista vacia donde se almacenara la matriz
     for i in range(filas): #se crea un ciclo for para elemento i en el rango de filas
        fila = [] # se crea una lista con las filas
        for j in range(columnas): #se crea un ciclo for para el elemento j en el rango de columnas 
            elemento = int(input(f"Ingrese el elemento [{i}][{j}]: ")) # se solicita ingresar los elementos en este formato
            fila.append(elemento) #se agrega el elemento en filas
        matriz.append(fila)# se agrega a la matriz
     return matriz

def sumar_columna(matriz, columna):
    """
    Suma los elementos de una columna dada de una matriz.

    Argumentos:
        matriz (list): La matriz.
        columna (int): El índice de la columna a sumar.

    Returns:
        int: La suma de los elementos de la columna.
    """
    suma = 0 #inicializamos una variable en 0
    for fila in matriz: #para cada fila de la matriz
        if columna < len(fila): # si la colunma es menor a la cantidad de filas
            suma += fila[columna]# sumar la columna dada
    return suma

if __name__ == "__main__":
 filas = int(input("Ingrese el número de filas de la matriz: "))
 columnas = int(input("Ingrese el número de columnas de la matriz: "))

 matriz = ingresar_matriz(filas, columnas)
 for fila in matriz:
  print (fila)
 # Solicitar al usuario la columna a sumar
 columna = int(input("Ingrese el número de columna a sumar: "))

 # Sumar los elementos de la columna
 suma_columna = sumar_columna(matriz, columna)

# Mostrar el resultado
 print(f"La suma de la columna {columna} es: {suma_columna}")
```
## Punto 5:
- Desarrollar un programa que sume los elementos de una columna dada de una matriz.
#### Explicación:
- 
```
def ingresar_matriz(filas, columnas): 
     """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
     matriz = [] # se crea una lista vacia donde se almacenara la matriz
     for i in range(filas): #se crea un ciclo for para elemento i en el rango de filas
        fila = [] # se crea una lista con las filas
        for j in range(columnas): #se crea un ciclo for para el elemento j en el rango de columnas 
            elemento = int(input(f"Ingrese el elemento [{i}][{j}]: ")) # se solicita ingresar los elementos en este formato
            fila.append(elemento) #se agrega el elemento en filas
        matriz.append(fila)# se agrega a la matriz
     return matriz
def sumar_fila(matriz, fila):
    """
    Suma los elementos de una fila dada de una matriz.

    Argumentos:
        matriz (list): La matriz.
        fila (int): El índice de la fila a sumar.

    Returns:
        int: La suma de los elementos de la fila.
    """
    suma = 0 #inicializamos la variable en 0
    if fila < len(matriz):# creamos un condicional que diga que si fila es menor que la cantidad de elementos de la matriz
        for elemento in matriz[fila]:# para cada elemento de la fila
            suma += elemento # sumar los elementos que hayan
    return suma

if __name__ == "__main__":
 filas = int(input("Ingrese el número de filas de la matriz: "))
 columnas = int(input("Ingrese el número de columnas de la matriz: "))

 matriz = ingresar_matriz(filas, columnas)
 for fila in matriz:
  print (fila)
 # Solicitar al usuario la columna a sumar
 fila = int(input("Ingrese el número de columna a sumar: "))

 # Sumar los elementos de la columna
 suma_fila = sumar_fila(matriz, fila)

# Mostrar el resultado
 print(f"La suma de la columna {fila} es: {suma_fila}")
```
# Las MATRICES son lo peor para enteder
## Pero se hizo el mayor intento y lo que no entendi toco pedir explicación:/
