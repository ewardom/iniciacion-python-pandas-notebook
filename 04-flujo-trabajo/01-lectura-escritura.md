# Lectura y Escritura de Datos

Cómo importar y exportar datos desde diferentes formatos.

## 📥 Leer Datos

### CSV (Comma-Separated Values)

```python
import pandas as pd

# Lectura básica
df = pd.read_csv('datos.csv')

# Con opciones comunes
df = pd.read_csv(
    'datos.csv',
    encoding='utf-8',      # Codificación
    sep=',',               # Delimitador (por defecto coma)
    decimal='.',           # Símbolo decimal
    nrows=1000,            # Leer solo primeras N filas
    skiprows=1,            # Saltar filas
    na_values=['NA', '']   # Valores que representan nulos
)

# TSV (Tab-Separated Values)
df = pd.read_csv('datos.tsv', sep='\t')

# Semicolon-separated (usado en países con coma como decimal)
df = pd.read_csv('datos.csv', sep=';', decimal=',')
```

### Excel

```python
# Lectura básica
df = pd.read_excel('datos.xlsx')

# Especificar hoja
df = pd.read_excel('datos.xlsx', sheet_name='Hoja1')
df = pd.read_excel('datos.xlsx', sheet_name=0)  # Primera hoja

# Leer múltiples hojas
dataframes = pd.read_excel('datos.xlsx', sheet_name=None)
# Devuelve un diccionario: {'Hoja1': df1, 'Hoja2': df2}

# Con opciones
df = pd.read_excel(
    'datos.xlsx',
    sheet_name='Datos',
    usecols=['nombre', 'edad'],  # Solo estas columnas
    dtype={'edad': int}            # Tipos específicos
)
```

### JSON

```python
# JSON simples
df = pd.read_json('datos.json')

# JSON con orientación específica
df = pd.read_json('datos.json', orient='records')
# 'records': [{'nombre': 'Juan', 'edad': 25}, ...]
df = pd.read_json('datos.json', orient='split')
# 'split': {'index': [...], 'columns': [...], 'data': [...]}
```

### SQL (Base de Datos)

```python
import sqlite3
from sqlalchemy import create_engine

# SQLite
conexion = sqlite3.connect('base_datos.db')
df = pd.read_sql_query('SELECT * FROM tabla', conexion)

# Usando SQLAlchemy (más potente)
engine = create_engine('sqlite:///base_datos.db')
df = pd.read_sql_table('tabla', engine)
```

### Otros Formatos

```python
# HDF5 (muy eficiente para datos grandes)
df = pd.read_hdf('datos.h5', key='datos')

# Stata
df = pd.read_stata('datos.dta')

# SQL Server
df = pd.read_sql('SELECT * FROM tabla', conexion)

# HTML
df = pd.read_html('https://ejemplo.com/tabla.html')  # ¡Desde web!
```

---

## 📤 Guardar Datos

### CSV

```python
# Guardar simple
df.to_csv('resultado.csv')

# Sin índice (recomendado)
df.to_csv('resultado.csv', index=False)

# Con opciones
df.to_csv(
    'resultado.csv',
    index=False,
    encoding='utf-8',
    sep=',',
    decimal='.'
)
```

### Excel

```python
# Guardar simple
df.to_excel('resultado.xlsx', index=False)

# Especificar hoja
df.to_excel('resultado.xlsx', sheet_name='Datos', index=False)

# Múltiples hojas
with pd.ExcelWriter('resultado.xlsx') as writer:
    df1.to_excel(writer, sheet_name='Hoja1', index=False)
    df2.to_excel(writer, sheet_name='Hoja2', index=False)
    df3.to_excel(writer, sheet_name='Hoja3', index=False)
```

### JSON

```python
# JSON simple
df.to_json('resultado.json', orient='records')

# JSON elegante (indentado)
df.to_json('resultado.json', orient='records', indent=2)

# Orientaciones
df.to_json('resultado.json', orient='split')    # Con estructura
df.to_json('resultado.json', orient='index')    # Indexado
df.to_json('resultado.json', orient='columns')  # Por columnas
```

### SQL

```python
# SQLite
conexion = sqlite3.connect('base_datos.db')
df.to_sql('mi_tabla', conexion, if_exists='replace', index=False)
# if_exists: 'fail' (error si existe), 'replace' (sobrescribir), 'append' (agregar)

# SQL Server / PostgreSQL
engine = create_engine('postgresql://usuario@localhost/basedatos')
df.to_sql('tabla', engine, if_exists='append')
```

### Otros Formatos

```python
# HDF5
df.to_hdf('datos.h5', key='datos', mode='w')

# Parquet (muy eficiente)
df.to_parquet('datos.parquet')

# Pickle (Python específico)
df.to_pickle('datos.pkl')
```

---

## 🔄 Ejemplo Completo: Lectura, Transformación, Guardado

```python
import pandas as pd

# 1. Leer datos
df = pd.read_csv('datos_brutos.csv')

# 2. Explorar
print(df.head())
print(df.info())

# 3. Limpiar
df = df.dropna()
df['edad'] = df['edad'].astype(int)

# 4. Transformar
df['año_nacimiento'] = 2024 - df['edad']

# 5. Guardar
df.to_csv('datos_limpios.csv', index=False)
df.to_excel('datos_limpios.xlsx', index=False)
print("✓ Datos guardados exitosamente")
```

---

## 💡 Tips Importantes

### Verificar Codificación

A veces los archivos tienen problemas de encoding:

```python
# Si te da error de codificación, intenta:
df = pd.read_csv('datos.csv', encoding='latin-1')
df = pd.read_csv('datos.csv', encoding='iso-8859-1')
df = pd.read_csv('datos.csv', encoding='cp1252')  # Windows
```

### Leer Archivos Muy Grandes

```python
# Leer en chunks (pedazos)
for chunk in pd.read_csv('datos_grandes.csv', chunksize=10000):
    procesar(chunk)  # Procesar cada parte

# O simplemente las primeras filas
df = pd.read_csv('datos_grandes.csv', nrows=1000)
```

### Ruta de Archivos

```python
import os

# Ruta relativa (desde donde está el script)
df = pd.read_csv('datos/archivo.csv')

# Ruta absoluta
df = pd.read_csv('/Users/usuario/datos/archivo.csv')

# Usar pathlib (moderno)
from pathlib import Path
ruta = Path('datos') / 'archivo.csv'
df = pd.read_csv(ruta)
```

---

**Siguiente:** [Limpieza de Datos →](02-limpieza-datos.md)
