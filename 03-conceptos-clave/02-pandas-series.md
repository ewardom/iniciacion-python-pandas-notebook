# Pandas: Series y DataFrames

Las dos estructuras de datos fundamentales de Pandas.

## 📊 ¿Qué es Pandas?

Pandas es la librería principal para análisis de datos en Python. Proporciona:
- Estructuras de datos eficientes
- Herramientas para limpieza de datos
- Opciones de análisis y agregación
- Integración con visualización

## 🔷 Series: Datos Unidimensionales

Una **Series** es como una columna de datos (similar a una lista, pero con superpoderes).

### Crear una Series

```python
import pandas as pd

# Desde una lista
edad = pd.Series([25, 30, 28, 35])
print(edad)
# Output:
# 0    25
# 1    30
# 2    28
# 3    35

# Con índice personalizado
edad = pd.Series(
    [25, 30, 28, 35],
    index=['Juan', 'María', 'Carlos', 'Ana']
)
print(edad)
# Output:
# Juan      25
# María     30
# Carlos    28
# Ana       35

# Desde un diccionario
edad = pd.Series({
    'Juan': 25,
    'María': 30,
    'Carlos': 28,
    'Ana': 35
})
```

### Acceder a Elementos

```python
# Por posición
print(edad[0])  # 25

# Por índice
print(edad['Juan'])  # 25

# Múltiples elementos
print(edad[0:2])  # Primeros dos

# Con condición
print(edad[edad > 28])  # Solo mayores de 28
```

### Operaciones con Series

```python
# Aritmética
print(edad + 1)      # Suma 1 a cada elemento
print(edad * 2)      # Multiplica cada elemento por 2

# Estadística
print(edad.mean())   # Promedio: 29.5
print(edad.max())    # Máximo: 35
print(edad.min())    # Mínimo: 25
print(edad.sum())    # Suma: 118

# Información
print(edad.describe())  # Resumen estadístico
```

## 🔲 DataFrame: Datos Bidimensionales

Un **DataFrame** es como una tabla o hoja de cálculo (filas y columnas).

### Crear un DataFrame

```python
# Desde un diccionario
df = pd.DataFrame({
    'nombre': ['Juan', 'María', 'Carlos', 'Ana'],
    'edad': [25, 30, 28, 35],
    'ciudad': ['Madrid', 'Barcelona', 'Valencia', 'Madrid'],
    'salario': [30000, 35000, 32000, 40000]
})

print(df)
```

**Output:**
```
    nombre     edad      ciudad  salario
0     Juan       25      Madrid    30000
1    María       30   Barcelona    35000
2   Carlos       28    Valencia    32000
3      Ana       35      Madrid    40000
```

### Acceder a Datos

```python
# Una columna (devuelve una Series)
print(df['edad'])
print(df.edad)  # Alternativa

# Múltiples columnas
print(df[['nombre', 'edad']])

# Una fila (devuelve una Series)
print(df.iloc[0])  # Primera fila por posición
print(df.loc[0])   # Primera fila por índice

# Múltiples filas
print(df[0:2])  # Primeras 2 filas

# Un valor específico
print(df.loc[0, 'nombre'])  # 'Juan'
print(df.iloc[0, 0])        # 'Juan'
```

### Filtrar DataFrames

```python
# Una condición
mayores_28 = df[df['edad'] > 28]

# Múltiples condiciones
madrid_mayores = df[(df['ciudad'] == 'Madrid') & (df['edad'] > 25)]

# Con .query()
mayores_28 = df.query('edad > 28')
```

### Información del DataFrame

```python
# Ver primeras filas
df.head()        # Primeras 5
df.head(2)       # Primeras 2

# Ver últimas filas
df.tail()

# Información general
df.info()        # Tipos de datos, valores nulos

# Resumen estadístico
df.describe()    # Media, desv. est., cuartiles

# Tamaño
print(df.shape)  # (4, 4) → 4 filas, 4 columnas
print(df.size)   # 16 → total de celdas

# Nombres de columnas
print(df.columns)  # Index(['nombre', 'edad', 'ciudad', 'salario'])
```

### Modificar el DataFrame

```python
# Agregar columna
df['experiencia'] = [2, 5, 3, 8]

# Renombrar columna
df = df.rename(columns={'edad': 'años'})

# Eliminar columna
df = df.drop('experiencia', axis=1)

# Cambiar un valor
df.loc[0, 'edad'] = 26

# Cambiar tipo de dato
df['edad'] = df['edad'].astype(int)
```

## 🔀 Series vs DataFrame

| Aspecto | Series | DataFrame |
|--------|--------|-----------|
| **Dimensiones** | 1D (columna) | 2D (tabla) |
| **Índice** | Sí, tiene índice | Sí, filas e índice de columnas |
| **Estructura** | Lista con índice | Diccionario de Series |
| **Uso típico** | Datos de una variable | Múltiples variables |

## 💡 Relación: DataFrame = Diccionario de Series

```python
# Cada columna es una Series
print(type(df['edad']))  # <class 'pandas.core.series.Series'>

# Puedo acceder como diccionario
print(df['edad'][0])  # 25

# Series individual
nombre_series = df['nombre']
print(nombre_series)
```

## 🏃 Performance: por qué Pandas es Rápido

```python
import time
import numpy as np

# Crear datos grandes
n = 1000000

# Con Python puro (lento)
inicio = time.time()
lista = [i * 2 for i in range(n)]
tiempo_python = time.time() - inicio

# Con NumPy (muy rápido)
inicio = time.time()
array = np.arange(n) * 2
tiempo_numpy = time.time() - inicio

# Con Pandas (muy rápido)
inicio = time.time()
series = pd.Series(range(n)) * 2
tiempo_pandas = time.time() - inicio

print(f"Python: {tiempo_python:.4f}s")
print(f"NumPy: {tiempo_numpy:.4f}s")
print(f"Pandas: {tiempo_pandas:.4f}s")
# NumPy y Pandas son 50-100x más rápidos
```

---

**Siguiente:** [Métodos Útiles →](04-metodos-utiles.md)
