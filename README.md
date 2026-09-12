[Introduccion_Vectores_Matrices_Google_Colab.ipynb](https://github.com/user-attachments/files/32139655/Introduccion_Vectores_Matrices_Google_Colab.ipynb)
{
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# Introducción a Vectores y Matrices con Python\n",
        "\n",
        "**Curso:** Introducción a Python / Álgebra Lineal  \n",
        "**Entorno:** Google Colab  \n",
        "**Biblioteca principal:** NumPy\n",
        "\n",
        "## Objetivos\n",
        "Al finalizar esta clase podrás:\n",
        "- Identificar qué es un vector y qué es una matriz.\n",
        "- Crear vectores y matrices con NumPy.\n",
        "- Acceder y modificar elementos mediante índices.\n",
        "- Realizar operaciones básicas con vectores.\n",
        "- Realizar operaciones básicas con matrices.\n",
        "- Diferenciar multiplicación elemento a elemento y multiplicación matricial.\n",
        "- Calcular productos punto y transpuestas.\n",
        "- Aplicar vectores y matrices a un problema sencillo.\n"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 1. Preparación del entorno\n",
        "\n",
        "Google Colab ya incluye NumPy, por lo que solamente necesitamos importarlo."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "import numpy as np\n",
        "\n",
        "print(\"NumPy versión:\", np.__version__)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 2. ¿Qué es un vector?\n",
        "\n",
        "Un **vector** es una colección ordenada de números. En NumPy podemos representarlo mediante un arreglo de una dimensión.\n",
        "\n",
        "Ejemplo matemático:\n",
        "\n",
        "$$v = [2, 4, 6]$$"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "vector = np.array([2, 4, 6])\n",
        "\n",
        "print(\"Vector:\", vector)\n",
        "print(\"Tipo de dato:\", type(vector))\n",
        "print(\"Dimensiones:\", vector.ndim)\n",
        "print(\"Cantidad de elementos:\", vector.size)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 3. Índices de un vector\n",
        "\n",
        "Python utiliza índices que comienzan en **0**. Por lo tanto, en `[10, 20, 30, 40, 50]`, el elemento `10` está en el índice `0`."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "vector = np.array([10, 20, 30, 40, 50])\n",
        "\n",
        "print(\"Vector:\", vector)\n",
        "print(\"Primer elemento:\", vector[0])\n",
        "print(\"Tercer elemento:\", vector[2])\n",
        "print(\"Último elemento:\", vector[-1])"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 4. Modificar elementos de un vector"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "vector = np.array([10, 20, 30, 40, 50])\n",
        "\n",
        "vector[1] = 25\n",
        "\n",
        "print(\"Vector modificado:\", vector)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 5. Operaciones básicas con vectores\n",
        "\n",
        "Si dos vectores tienen la misma cantidad de elementos, podemos realizar operaciones elemento a elemento."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([1, 2, 3])\n",
        "B = np.array([4, 5, 6])\n",
        "\n",
        "print(\"A =\", A)\n",
        "print(\"B =\", B)\n",
        "print(\"A + B =\", A + B)\n",
        "print(\"A - B =\", A - B)\n",
        "print(\"A * B =\", A * B)\n",
        "print(\"A / B =\", A / B)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 6. Multiplicación de un vector por un escalar\n",
        "\n",
        "Un escalar es un número. Multiplicar un vector por un escalar multiplica cada elemento por ese número."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "vector = np.array([2, 4, 6])\n",
        "escalar = 3\n",
        "\n",
        "resultado = escalar * vector\n",
        "\n",
        "print(\"Vector:\", vector)\n",
        "print(\"Escalar:\", escalar)\n",
        "print(\"Resultado:\", resultado)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 7. Producto punto\n",
        "\n",
        "El producto punto entre dos vectores produce un único número.\n",
        "\n",
        "Para:\n",
        "\n",
        "$$A=[1,2,3]$$\n",
        "$$B=[4,5,6]$$\n",
        "\n",
        "tenemos:\n",
        "\n",
        "$$(1)(4)+(2)(5)+(3)(6)=32$$"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([1, 2, 3])\n",
        "B = np.array([4, 5, 6])\n",
        "\n",
        "producto_punto = np.dot(A, B)\n",
        "\n",
        "print(\"Producto punto:\", producto_punto)\n",
        "print(\"También podemos usar @:\", A @ B)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 8. Norma de un vector\n",
        "\n",
        "La norma euclidiana representa la longitud de un vector.\n",
        "\n",
        "$$||v|| = \\sqrt{v_1^2+v_2^2+...+v_n^2}$$"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "v = np.array([3, 4])\n",
        "\n",
        "norma = np.linalg.norm(v)\n",
        "\n",
        "print(\"Vector:\", v)\n",
        "print(\"Norma:\", norma)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 9. ¿Qué es una matriz?\n",
        "\n",
        "Una **matriz** es una colección de números organizada en filas y columnas.\n",
        "\n",
        "Ejemplo:\n",
        "\n",
        "$$A=\\begin{bmatrix}1&2&3\\\\4&5&6\\end{bmatrix}$$\n",
        "\n",
        "Esta matriz tiene 2 filas y 3 columnas."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2, 3],\n",
        "    [4, 5, 6]\n",
        "])\n",
        "\n",
        "print(A)\n",
        "print(\"Número de dimensiones:\", A.ndim)\n",
        "print(\"Forma (filas, columnas):\", A.shape)\n",
        "print(\"Cantidad de elementos:\", A.size)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 10. Acceder a elementos de una matriz\n",
        "\n",
        "Usamos `matriz[fila, columna]`. Los índices comienzan en 0."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [10, 20, 30],\n",
        "    [40, 50, 60]\n",
        "])\n",
        "\n",
        "print(\"Elemento [0, 0]:\", A[0, 0])\n",
        "print(\"Elemento [0, 2]:\", A[0, 2])\n",
        "print(\"Elemento [1, 1]:\", A[1, 1])"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 11. Seleccionar filas y columnas\n",
        "\n",
        "Podemos seleccionar una fila completa, una columna completa o una sección de la matriz."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2, 3],\n",
        "    [4, 5, 6],\n",
        "    [7, 8, 9]\n",
        "])\n",
        "\n",
        "print(\"Matriz completa:\\n\", A)\n",
        "print(\"\\nPrimera fila:\", A[0, :])\n",
        "print(\"Segunda columna:\", A[:, 1])\n",
        "print(\"Submatriz 2x2:\\n\", A[0:2, 0:2])"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 12. Suma y resta de matrices\n",
        "\n",
        "Para sumar o restar matrices deben tener dimensiones compatibles; en el caso básico, ambas tienen la misma forma."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2],\n",
        "    [3, 4]\n",
        "])\n",
        "\n",
        "B = np.array([\n",
        "    [5, 6],\n",
        "    [7, 8]\n",
        "])\n",
        "\n",
        "print(\"A + B:\\n\", A + B)\n",
        "print(\"\\nA - B:\\n\", A - B)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 13. Multiplicación por un escalar"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2],\n",
        "    [3, 4]\n",
        "])\n",
        "\n",
        "print(\"3A =\\n\", 3 * A)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 14. Multiplicación elemento a elemento vs. multiplicación matricial\n",
        "\n",
        "Con NumPy, `A * B` multiplica elemento a elemento. En cambio, `A @ B` realiza la multiplicación matricial."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2],\n",
        "    [3, 4]\n",
        "])\n",
        "\n",
        "B = np.array([\n",
        "    [5, 6],\n",
        "    [7, 8]\n",
        "])\n",
        "\n",
        "print(\"Multiplicación elemento a elemento:\")\n",
        "print(A * B)\n",
        "\n",
        "print(\"\\nMultiplicación matricial:\")\n",
        "print(A @ B)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "### ¿Cómo se calcula `A @ B`?\n",
        "\n",
        "Para el primer elemento:\n",
        "\n",
        "$$(1)(5)+(2)(7)=19$$\n",
        "\n",
        "Para el segundo elemento:\n",
        "\n",
        "$$(1)(6)+(2)(8)=22$$"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 15. Transpuesta de una matriz\n",
        "\n",
        "La transpuesta intercambia filas por columnas."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [1, 2, 3],\n",
        "    [4, 5, 6]\n",
        "])\n",
        "\n",
        "print(\"Matriz original:\\n\", A)\n",
        "print(\"\\nMatriz transpuesta:\\n\", A.T)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 16. Matrices especiales\n",
        "\n",
        "NumPy permite crear rápidamente matrices de ceros, unos e identidad."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "print(\"Matriz de ceros:\")\n",
        "print(np.zeros((3, 3)))\n",
        "\n",
        "print(\"\\nMatriz de unos:\")\n",
        "print(np.ones((2, 4)))\n",
        "\n",
        "print(\"\\nMatriz identidad:\")\n",
        "print(np.eye(3))"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## 17. Estadísticas básicas de una matriz\n",
        "\n",
        "Podemos calcular suma, promedio, máximo y mínimo. El parámetro `axis=0` trabaja por columnas y `axis=1` por filas."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "calificaciones = np.array([\n",
        "    [85, 90, 95],\n",
        "    [70, 80, 75],\n",
        "    [95, 92, 98]\n",
        "])\n",
        "\n",
        "print(\"Calificaciones:\\n\", calificaciones)\n",
        "print(\"\\nPromedio por alumno:\", np.mean(calificaciones, axis=1))\n",
        "print(\"Promedio por materia:\", np.mean(calificaciones, axis=0))\n",
        "print(\"Promedio general:\", np.mean(calificaciones))\n",
        "print(\"Calificación máxima:\", np.max(calificaciones))\n",
        "print(\"Calificación mínima:\", np.min(calificaciones))"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 18. Aplicación: ventas de una tienda\n",
        "\n",
        "Supongamos que una tienda vende tres productos durante cuatro días.\n",
        "\n",
        "- Filas = días\n",
        "- Columnas = productos\n",
        "- Producto 1, Producto 2 y Producto 3\n",
        "\n",
        "La matriz representa la cantidad de unidades vendidas."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "ventas = np.array([\n",
        "    [10, 15, 8],\n",
        "    [12, 10, 11],\n",
        "    [8, 20, 10],\n",
        "    [15, 18, 12]\n",
        "])\n",
        "\n",
        "print(\"Ventas:\\n\", ventas)\n",
        "print(\"\\nTotal vendido por producto:\", np.sum(ventas, axis=0))\n",
        "print(\"Total vendido por día:\", np.sum(ventas, axis=1))\n",
        "print(\"Total de unidades vendidas:\", np.sum(ventas))"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 19. Ejercicio 1 — Vectores\n",
        "\n",
        "Crea los vectores:\n",
        "\n",
        "$$A=[5,10,15,20]$$\n",
        "$$B=[2,4,6,8]$$\n",
        "\n",
        "Calcula:\n",
        "1. `A + B`\n",
        "2. `A - B`\n",
        "3. `A * B`\n",
        "4. `A / B`\n",
        "5. El producto punto de `A` y `B`."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "# Escribe aquí tu solución\n",
        "\n",
        "A = np.array([5, 10, 15, 20])\n",
        "B = np.array([2, 4, 6, 8])\n",
        "\n",
        "# 1. Suma\n",
        "# 2. Resta\n",
        "# 3. Multiplicación\n",
        "# 4. División\n",
        "# 5. Producto punto"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## Solución del ejercicio 1\n",
        "\n",
        "Puedes ejecutar esta celda después de intentar resolverlo por tu cuenta."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([5, 10, 15, 20])\n",
        "B = np.array([2, 4, 6, 8])\n",
        "\n",
        "print(\"A + B =\", A + B)\n",
        "print(\"A - B =\", A - B)\n",
        "print(\"A * B =\", A * B)\n",
        "print(\"A / B =\", A / B)\n",
        "print(\"Producto punto =\", np.dot(A, B))"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 20. Ejercicio 2 — Matrices\n",
        "\n",
        "Sean:\n",
        "\n",
        "$$A=\\begin{bmatrix}2&4\\\\6&8\\end{bmatrix}$$\n",
        "$$B=\\begin{bmatrix}1&3\\\\5&7\\end{bmatrix}$$\n",
        "\n",
        "Calcula:\n",
        "1. `A + B`\n",
        "2. `A - B`\n",
        "3. `A * B`\n",
        "4. `A @ B`\n",
        "5. `A.T`"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "# Escribe aquí tu solución\n",
        "\n",
        "A = np.array([\n",
        "    [2, 4],\n",
        "    [6, 8]\n",
        "])\n",
        "\n",
        "B = np.array([\n",
        "    [1, 3],\n",
        "    [5, 7]\n",
        "])\n",
        "\n",
        "# Completa las operaciones"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## Solución del ejercicio 2"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "A = np.array([\n",
        "    [2, 4],\n",
        "    [6, 8]\n",
        "])\n",
        "\n",
        "B = np.array([\n",
        "    [1, 3],\n",
        "    [5, 7]\n",
        "])\n",
        "\n",
        "print(\"A + B:\\n\", A + B)\n",
        "print(\"\\nA - B:\\n\", A - B)\n",
        "print(\"\\nA * B:\\n\", A * B)\n",
        "print(\"\\nA @ B:\\n\", A @ B)\n",
        "print(\"\\nA transpuesta:\\n\", A.T)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 21. Reto final\n",
        "\n",
        "Una escuela tiene las calificaciones de cuatro estudiantes en tres materias:\n",
        "\n",
        "- Matemáticas\n",
        "- Física\n",
        "- Programación\n",
        "\n",
        "Usa la siguiente matriz:\n",
        "\n",
        "```text\n",
        "[[80, 75, 90],\n",
        " [95, 88, 92],\n",
        " [70, 85, 78],\n",
        " [90, 92, 95]]\n",
        "```\n",
        "\n",
        "Realiza lo siguiente:\n",
        "1. Crear la matriz con NumPy.\n",
        "2. Mostrar sus dimensiones.\n",
        "3. Calcular el promedio de cada estudiante.\n",
        "4. Calcular el promedio de cada materia.\n",
        "5. Encontrar la calificación máxima.\n",
        "6. Encontrar la calificación mínima.\n",
        "7. Determinar qué estudiante tiene el promedio más alto."
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "# Reto final: intenta resolverlo sin mirar la solución.\n",
        "\n",
        "calificaciones = np.array([\n",
        "    [80, 75, 90],\n",
        "    [95, 88, 92],\n",
        "    [70, 85, 78],\n",
        "    [90, 92, 95]\n",
        "])\n",
        "\n",
        "# Completa el código aquí."
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "## Solución del reto final"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {},
      "outputs": [],
      "source": [
        "calificaciones = np.array([\n",
        "    [80, 75, 90],\n",
        "    [95, 88, 92],\n",
        "    [70, 85, 78],\n",
        "    [90, 92, 95]\n",
        "])\n",
        "\n",
        "promedios_estudiantes = np.mean(calificaciones, axis=1)\n",
        "promedios_materias = np.mean(calificaciones, axis=0)\n",
        "maxima = np.max(calificaciones)\n",
        "minima = np.min(calificaciones)\n",
        "mejor_estudiante = np.argmax(promedios_estudiantes) + 1\n",
        "\n",
        "print(\"Dimensiones:\", calificaciones.shape)\n",
        "print(\"Promedio de cada estudiante:\", promedios_estudiantes)\n",
        "print(\"Promedio de cada materia:\", promedios_materias)\n",
        "print(\"Calificación máxima:\", maxima)\n",
        "print(\"Calificación mínima:\", minima)\n",
        "print(\"Estudiante con mayor promedio: Estudiante\", mejor_estudiante)"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {},
      "source": [
        "# 22. Resumen de la clase\n",
        "\n",
        "| Concepto | NumPy |\n",
        "|---|---|\n",
        "| Crear vector | `np.array([1, 2, 3])` |\n",
        "| Crear matriz | `np.array([[1, 2], [3, 4]])` |\n",
        "| Dimensiones | `.shape` |\n",
        "| Número de dimensiones | `.ndim` |\n",
        "| Cantidad de elementos | `.size` |\n",
        "| Producto punto | `np.dot(A, B)` |\n",
        "| Multiplicación elemento a elemento | `A * B` |\n",
        "| Multiplicación matricial | `A @ B` |\n",
        "| Transpuesta | `A.T` |\n",
        "| Norma | `np.linalg.norm(A)` |\n",
        "| Matriz de ceros | `np.zeros((filas, columnas))` |\n",
        "| Matriz de unos | `np.ones((filas, columnas))` |\n",
        "| Matriz identidad | `np.eye(n)` |\n",
        "\n",
        "## Ideas clave\n",
        "\n",
        "- Un **vector** puede entenderse como una lista ordenada de números.\n",
        "- Una **matriz** organiza números en filas y columnas.\n",
        "- Los índices de Python comienzan en `0`.\n",
        "- `*` en NumPy realiza multiplicación elemento a elemento.\n",
        "- `@` realiza multiplicación matricial.\n",
        "- `axis=0` permite trabajar por columnas y `axis=1` por filas.\n",
        "- NumPy facilita las operaciones matemáticas con vectores y matrices."
      ]
    }
  ],
  "metadata": {
    "kernelspec": {
      "display_name": "Python 3",
      "language": "python",
      "name": "python3"
    },
    "language_info": {
      "name": "python",
      "version": "3"
    },
    "colab": {
      "name": "Introducción a Vectores y Matrices con Python.ipynb",
      "provenance": []
    }
  },
  "nbformat": 4,
  "nbformat_minor": 5
}
