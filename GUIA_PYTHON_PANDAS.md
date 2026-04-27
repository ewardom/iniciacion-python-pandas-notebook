# Guía de Iniciación: Python, Pandas y Jupyter Notebooks

## Introducción

Esta guía te enseñará los fundamentos de Python aplicados al análisis de datos usando **Pandas** y **Jupyter Notebooks**. Es una guía práctica centrada en conceptos clave y flujos de trabajo reales.

---

## 📚 Índice

1. [¿Qué es Jupyter Notebook?](#qué-es-jupyter-notebook)
2. [Instalación](#instalación)
3. [Conceptos Clave](#conceptos-clave)
4. [Flujo de Trabajo con Pandas](#flujo-de-trabajo-con-pandas)
5. [Buenas Prácticas](#buenas-prácticas)

---

## ¿Qué es Jupyter Notebook?

Jupyter Notebook es una aplicación web que te permite crear documentos interactivos llamados **cuadernos** (`.ipynb`).

### Características principales:

- **Ejecución por celdas**: Ejecuta código en partes, no necesariamente todo de una vez
- **Visualización en tiempo real**: Ve resultados inmediatamente después de ejecutar cada celda
- **Mezcla de código y documentación**: Combina código Python con texto, imágenes y markdown
- **Perfecto para análisis exploratorio**: Ideal para investigar datos y experimentar

### Ventajas para análisis de datos:

✅ Visualiza resultados mientras trabajas  
✅ Documenta tu proceso de análisis  
✅ Facilita la presentación de resultados  
✅ Permite revisar y modificar código fácilmente  

---

## Instalación

### Instalación de dependencias

```bash
pip install pandas numpy matplotlib seaborn
```

### Instalar la Extensión de Jupyter en VS Code

1. **Abre VS Code**
2. Ve a la sección **Extensiones** (icono cuadrado de 4 bloques en la barra lateral izquierda o presiona `Cmd+Shift+X`)
3. Busca **"Jupyter"** en la barra de búsqueda
4. Haz clic en la extensión oficial **"Jupyter"** de Microsoft
5. Presiona el botón **"Install"** (Instalar)

Alternativamente, puedes instalar desde terminal:
```bash
code --install-extension ms-toolsai.jupyter
```

### Usar Jupyter Notebooks en VS Code

Una vez instalada la extensión:

1. Crea un archivo nuevo con extensión `.ipynb` (por ejemplo: `analisis.ipynb`)
2. VS Code reconocerá automáticamente el formato de Jupyter Notebook
3. Comienza a escribir código en celdas y ejecuta con `Shift+Enter`

La extensión incluye la capacidad de crear, editar y ejecutar notebooks directamente en VS Code sin necesidad de abrir el navegador.

---

## Conceptos Clave

### 1. **Si repites código, crea una función**

**Mal:**
```python
resultado1 = datos1 * 2
resultado2 = datos2 * 2
resultado3 = datos3 * 2
```

**Bien:**
```python
def multiplicar_por_dos(datos):
    return datos * 2

resultado1 = multiplicar_por_dos(datos1)
resultado2 = multiplicar_por_dos(datos2)
resultado3 = multiplicar_por_dos(datos3)
```

### 2. **Pandas es tu librería por excelencia**

Pandas es la herramienta principal para análisis de datos en Python. Sus estructuras clave son:

- **Series**: Datos unidimensionales (columna)
- **DataFrame**: Datos bidimensionales (tabla)

```python
import pandas as pd

# Crear un DataFrame
df = pd.DataFrame({
    'nombre': ['Juan', 'María', 'Carlos'],
    'edad': [25, 30, 28],
    'ciudad': ['Madrid', 'Barcelona', 'Valencia']
})

print(df)
```

### 3. **La mayoría de las veces ya existe un método**

**Investigar antes de crear desde cero:**

- ¿Necesitas filtrar datos? → Usa `.loc[]` o `.query()`
- ¿Necesitas contar valores? → Usa `.value_counts()`
- ¿Necesitas obtener estadísticas? → Usa `.describe()`
- ¿Necesitas reemplazar valores? → Usa `.replace()`

```python
# En lugar de hacer un bucle para contar, usa:
df['ciudad'].value_counts()  # ✅ Mucho más rápido

# En lugar de filtrar manualmente, usa:
df[df['edad'] > 25]  # ✅ Una línea, limpio y eficiente
```

---

## Flujo de Trabajo con Pandas

### 1. **Lectura/Escritura de Datos**

```python
import pandas as pd

# Leer CSV
df = pd.read_csv('datos.csv')

# Leer Excel
df = pd.read_excel('datos.xlsx')

# Leer JSON
df = pd.read_json('datos.json')

# Guardar como CSV
df.to_csv('resultado.csv', index=False)

# Guardar como Excel
df.to_excel('resultado.xlsx', index=False)
```

### 2. **Limpieza y Transformación de Datos**

```python
# Ver primeras filas
df.head()

# Ver información del DataFrame
df.info()

# Verificar valores nulos
df.isnull().sum()

# Eliminar filas con valores nulos
df = df.dropna()

# Rellenar valores nulos
df['edad'] = df['edad'].fillna(0)

# Renombrar columnas
df = df.rename(columns={'edad': 'años'})

# Cambiar tipos de datos
df['fecha'] = pd.to_datetime(df['fecha'])
```

### 3. **Agrupación y Agregación (groupby)**

```python
# Agrupar por ciudad y calcular promedio de edad
promedio_por_ciudad = df.groupby('ciudad')['edad'].mean()

# Múltiples agregaciones
resumen = df.groupby('ciudad').agg({
    'edad': ['mean', 'min', 'max'],
    'nombre': 'count'  # Contar registros
})

# Renombrar columnas del resultado
resumen.columns = ['edad_promedio', 'edad_minima', 'edad_maxima', 'cantidad']
```

### 4. **Merge y Join de Datasets**

```python
# Merge (JOIN similar a SQL)
df_resultado = pd.merge(df1, df2, on='id', how='inner')
# Tipos: 'inner', 'outer', 'left', 'right'

# Concatenar DataFrames
df_concatenado = pd.concat([df1, df2], ignore_index=True)

# Unir por índice
df_resultado = df1.join(df2, rsuffix='_derecha')
```

### 5. **Visualización Clara de Resultados**

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Gráfico de barras
df['ciudad'].value_counts().plot(kind='bar', title='Cantidad por ciudad')
plt.show()

# Histograma
df['edad'].hist(bins=10, title='Distribución de edades')
plt.show()

# Scatter plot
plt.scatter(df['edad'], df['ingresos'])
plt.xlabel('Edad')
plt.ylabel('Ingresos')
plt.show()

# Heatmap de correlación
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.show()
```

---

## Buenas Prácticas

### En Jupyter Notebooks:

✅ **Una idea por celda**: Mantén celdas pequeñas y enfocadas  
✅ **Documenta con Markdown**: Explica qué hace cada sección  
✅ **Ejecuta celdas en orden**: De arriba hacia abajo  
✅ **Reinicia el kernel regularmente**: Asegura un estado limpio  
✅ **Visualiza datos frecuentemente**: No esperes al final  

### En Python/Pandas:

✅ **Usa nombres descriptivos**: `edad_promedio` en lugar de `ap`  
✅ **Verifica tus datos**: Siempre revisa con `.head()` e `.info()`  
✅ **Documenta tu lógica**: Comenta código complejo  
✅ **Evita modificar datos originales**: Crea copias cuando necesites  
✅ **Aprovecha métodos Pandas**: Antes de escribir código, busca si existe un método  

---

## Estructura de un Notebook de Análisis Típico

```
1. Importar librerías
2. Cargar datos
3. Exploración inicial (head, info, describe)
4. Limpieza de datos
5. Transformación de datos
6. Análisis y agregaciones
7. Visualización de resultados
8. Conclusiones
```

---

## Recursos Útiles

- [Documentación oficial de Pandas](https://pandas.pydata.org/docs/)
- [Documentación oficial de Jupyter](https://jupyter.org/)
- [Cheat Sheet de Pandas](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
- [Kaggle Datasets](https://www.kaggle.com/datasets) - Datos para practicar

---

## Conclusión

El análisis de datos con Python es un proceso iterativo:

1. **Cargar** datos
2. **Explorar** y **limpiar**
3. **Transformar** y **agregar**
4. **Visualizar** resultados
5. **Documentar** conclusiones

Jupyter Notebooks te permite hacer todo esto de forma interactiva y transparente. ¡Practica con datos reales y verás cómo mejoras rápidamente!

---

**¡Buena suerte en tu camino en el análisis de datos! 🚀**