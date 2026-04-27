# Métodos Útiles de Pandas

Métodos esenciales que usarás constantemente.

## 🔍 El Principio Clave

> **"Antes de escribir código, busca si existe un método en Pandas"**

La mayoría de las operaciones ya han sido optimizadas en Pandas.

## 📚 Métodos Más Utilizados

### 1️⃣ Contar Valores: `.value_counts()`

```python
# ❌ Mal: hacer un bucle
contador = {}
for ciudad in df['ciudad']:
    if ciudad in contador:
        contador[ciudad] += 1
    else:
        contador[ciudad] = 1

# ✅ Bien: usar value_counts()
df['ciudad'].value_counts()
# Madrid        2
# Barcelona     1
# Valencia      1
```

### 2️⃣ Filtrar Datos: `.loc[]` y `.query()`

```python
# ✅ Método 1: loc
mayores_28 = df.loc[df['edad'] > 28]

# ✅ Método 2: query (más legible)
mayores_28 = df.query('edad > 28')

# ✅ Múltiples condiciones
resultado = df.query('edad > 28 and ciudad == "Madrid"')
```

### 3️⃣ Obtener Estadísticas: `.describe()`

```python
# En lugar de calcular uno a uno
df['edad'].describe()
# count     4.00
# mean     29.50
# std       4.43
# min      25.00
# 25%      27.00
# 50%      29.00
# 75%      32.50
# max      35.00

# Para todo el DataFrame
df.describe()
```

### 4️⃣ Reemplazar Valores: `.replace()`

```python
# ❌ Mal: pasar columna y reasignar
df['ciudad'] = df['ciudad'].apply(
    lambda x: 'Madrid' if x == 'Mdr' else x
)

# ✅ Bien: usar replace
df['ciudad'] = df['ciudad'].replace({
    'Mdr': 'Madrid',
    'Bcn': 'Barcelona',
    'Val': 'Valencia'
})

# Incluso más simple
df['ciudad'] = df['ciudad'].replace('Mdr', 'Madrid')
```

### 5️⃣ Aplicar Funciones: `.apply()`

```python
# Aplicar a una columna
def categorizar(edad):
    return 'Mayor' if edad > 30 else 'Joven'

df['categoria'] = df['edad'].apply(categorizar)

# Aplicar a varias columnas
df[['edad', 'salario']] = df[['edad', 'salario']].apply(
    lambda x: (x - x.mean()) / x.std()
)  # Normalizar
```

### 6️⃣ Valores Únicos: `.unique()` y `.nunique()`

```python
# Valores únicos
print(df['ciudad'].unique())  # ['Madrid', 'Barcelona', 'Valencia']

# Cantidad de valores únicos
print(df['ciudad'].nunique())  # 3

# Ver con counts (similar a value_counts pero dataframe)
print(pd.Series(df['ciudad']).value_counts())
```

### 7️⃣ Agrupar: `.groupby()`

```python
# Promedio por ciudad
df.groupby('ciudad')['salario'].mean()
# Madrid        35000.0
# Barcelona     35000.0
# Valencia      32000.0

# Múltiples agregaciones
df.groupby('ciudad')['salario'].agg(['mean', 'min', 'max'])

# Renombrar resultados
resumen = df.groupby('ciudad').agg({
    'edad': 'mean',
    'salario': ['min', 'max', 'mean']
}).round(2)
```

### 8️⃣ Verificar Valores Nulos: `.isnull()`, `.notnull()`, `.fillna()`

```python
# Ver dónde hay valores nulos
print(df.isnull())

# Contar nulos por columna
print(df.isnull().sum())

# Eliminar filas con nulos
df_limpio = df.dropna()

# Llenar nulos con un valor
df['edad'] = df['edad'].fillna(0)

# Llenar nulos con el promedio
df['edad'] = df['edad'].fillna(df['edad'].mean())
```

### 9️⃣ Renombrar Columnas: `.rename()`

```python
# Rename específico
df = df.rename(columns={'edad': 'años', 'salario': 'sueldo'})

# Cambiar todo a mayúscula
df.columns = df.columns.str.upper()
```

### 🔟 Ordenar: `.sort_values()`

```python
# Ordenar por una columna
df_ordenado = df.sort_values('edad')

# Descendente
df_ordenado = df.sort_values('edad', ascending=False)

# Por múltiples columnas
df_ordenado = df.sort_values(['ciudad', 'edad'])
```

## 🚀 Métodos para Transformación Rápida

### Aplicar Cálculo a Toda una Columna

```python
# ❌ Mal: hacer un bucle
ingresos_anuales = []
for salario in df['salario']:
    ingresos_anuales.append(salario * 12)

# ✅ Bien: operación vectorizada
df['ingreso_anual'] = df['salario'] * 12  # ¡Mucho más rápido!
```

### Convertir Tipos de Datos

```python
# Convertir a int
df['edad'] = df['edad'].astype(int)

# Convertir a string
df['id_string'] = df['id'].astype(str)

# Convertir a datetime
df['fecha'] = pd.to_datetime(df['fecha'])

# Categoría (útil para ahorrar memoria)
df['ciudad'] = df['ciudad'].astype('category')
```

### Crear Nuevas Columnas con `.assign()`

```python
# Sin modificar el original
df_nuevo = df.assign(
    edad_en_10_anos=df['edad'] + 10,
    salario_mensual=df['salario'] / 12
)
```

## 📊 Métodos para Exploración

```python
# Resumen rápido
df.info()          # Tipos y memoria
df.describe()      # Estadísticas
df.head()          # Primeras filas
df.tail()          # Últimas filas
df.sample(n=2)     # Muestra aleatoria

# Correlaciones
df.corr()          # Matriz de correlación

# Duplicados
df.duplicated()    # Dónde hay duplicados
df.drop_duplicates()  # Eliminar duplicados
```

## 💡 Regla del 80/20

Estos 10 métodos resuelven el **80% de casos**:

1. `.value_counts()` — Contar
2. `.loc[]` — Filtrar
3. `.query()` — Filtrar legible
4. `.describe()` — Estadísticas
5. `.replace()` — Reemplazar
6. `.apply()` — Función a columna
7. `.groupby()` — Agrupar
8. `.fillna()` — Llenar nulos
9. `.sort_values()` — Ordenar
10. `.drop_duplicates()` — Eliminar dupes

---

**Siguiente:** [Flujo de Trabajo →](../04-flujo-trabajo/01-lectura-escritura.md)
