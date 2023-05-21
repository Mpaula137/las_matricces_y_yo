# las_matricces_y_yo
Reto #11, matrices y demás funciones:)
## Primer punto:
- Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
### Explicación:
- Tenemos que tener en cuenta que las dos matrices deben tener la misma cantidad de elementos pra poder realizar alguna operación, asi que realice un función con ayuda de un condicional que verifica con un len si las matrices son iguales, se suma el elemento [0][0] de la matriz1 y el mismo elemento de la matriza2.
```
def validar_matrices(m1, m2):
    """
    Verifica si las matrices tienen las mismas dimensiones.

    Argumentos:
        matriz1(m1)-(list): La primera matriz.
        matriz2(m2)-(list): La segunda matriz.

    Return:
        bool: True si las matrices tienen las mismas dimensiones, False en caso contrario.
    """
    # Verificar si las matrices tienen las mismas dimensiones
    if len(m1) != len(m2) or len(m1[0]) != len(m2[0]):
        print("Las matrices no tienen las mismas dimensiones.")
        return False

    return True


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


# Ejemplo de uso del programa
matriz1 = [[65, 23, 4], [2, 13, 43]]
matriz2 = [[12, 2, 34], [17, 14, 15]]

if validar_matrices(matriz1, matriz2):# usamos el condicional para validar si son iguales
    print("Suma de matrices:")
    resultado_suma = sumar_matrices(matriz1, matriz2)#llamamos la funcion para sumar
    for fila in resultado_suma:
        print(fila)

    print("Resta de matrices:")
    resultado_resta = restar_matrices(matriz1, matriz2)#llamamos la funcion para restar
    for fila in resultado_resta:
        print(fila)
```
## Punto 2:
- Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
### Explicación: 
- Tenemos que tener en cuenta que las dos matrices deben tener la misma cantidad de elementos pra poder realizar alguna operación, asi que realice un función con ayuda de un condicional que verifica con un len si las matrices son iguales, se resta el elemento [0][0] de la matriz1 y el mismo elemento de la matriza2.
```
def validar_matrices_multiplicacion(matriz1, matriz2):
    """
    Verifica si las matrices pueden ser multiplicadas.

    Argumentos:
        matriz1 (list): La primera matriz.
        matriz2 (list): La segunda matriz.

    Returns:
        bool: True si las matrices pueden ser multiplicadas, False en caso contrario.
    """
    # Verificar si el número de columnas de matriz1 es igual al número de filas de matriz2
    if len(matriz1[0]) != len(matriz2):
        print("Las matrices no cumplen las condiciones para la multiplicación.")
        return False

    return True


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


# Ejemplo de uso del programa
matriz1 = [[1, 2, 3], [4, 5, 6]]
matriz2 = [[7, 8], [9, 10], [11, 12]]

if validar_matrices_multiplicacion(matriz1, matriz2):
    print("Producto de matrices:")
    resultado_producto = multiplicar_matrices(matriz1, matriz2)
    for fila in resultado_producto:
        print(fila)
```
## Punto 3:
- Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.
### Explicación: 
-
```
d
```
## Punto 4:
- Desarrollar un programa que sume los elementos de una columna dada de una matriz.
#### Explicación:
```

```
## Punto 5:
- Desarrollar un programa que sume los elementos de una columna dada de una matriz.
### Explicación:
