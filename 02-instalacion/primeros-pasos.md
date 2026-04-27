# Primeros Pasos

Tu primer notebook desde cero.

## 🎯 Objetivo

Crear tu primer notebook funcional y productivo.

## 📝 Crear um Notebook Nuevo

1. En VS Code, crea un archivo: `mi_primer_notebook.ipynb`
2. VS Code detectará automáticamente el formato
3. Verás la interfaz de Jupyter

## 🏗️ Estructura Básica de un Notebook

Copiar y ejecutar celda por celda:

### 1️⃣ Celda 1: Importar Librerías

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

print("✓ Librerías cargadas correctamente")
```

**Resultado esperado:** ✓ Librerías cargadas correctamente

### 2️⃣ Celda 2: Crear Datos de Ejemplo

```python
# Crear un DataFrame simple
data = {
    'nombre': ['Juan', 'María', 'Carlos', 'Ana'],
    'edad': [25, 30, 28, 35],
    'ciudad': ['Madrid', 'Barcelona', 'Valencia', 'Madrid'],
    'salario': [30000, 35000, 32000, 40000]
}

df = pd.DataFrame(data)
print(df)
```

**Resultado esperado:** Una tabla con 4 personas

### 3️⃣ Celda 3: Explorar los Datos

```python
# Ver información del DataFrame
print("Información del DataFrame:")
print(df.info())
print("\n")

# Estadísticas básicas
print("Estadísticas:")
print(df.describe())
```

### 4️⃣ Celda 4: Filtrar Datos

```python
# Persona mayores de 28 años
personas_mayores = df[df['edad'] > 28]
print("Personas mayores de 28 años:")
print(personas_mayores)
```

### 5️⃣ Celda 5: Agrupar Datos

```python
# Salario promedio por ciudad
salario_por_ciudad = df.groupby('ciudad')['salario'].mean()
print("Salario promedio por ciudad:")
print(salario_por_ciudad)
```

### 6️⃣ Celda 6: Crear una Visualización

```python
# Gráfico de edades
plt.figure(figsize=(10, 6))
plt.bar(df['nombre'], df['edad'], color='skyblue')
plt.xlabel('Nombre')
plt.ylabel('Edad')
plt.title('Edades de los Empleados')
plt.grid(axis='y', alpha=0.3)
plt.show()
```

### 7️⃣ Celda 7 (Markdown): Conclusiones

```markdown
# Análisis Completado ✓

## Hallazgos Principales

- **Total de registros:** 4 personas
- **Edad promedio:** 29.5 años
- **Salario promedio:** 34,250€
- **Ciudades:** Madrid, Barcelona, Valencia

## Próximos Pasos

1. Recopilar más datos
2. Analizar tendencias anuales
3. Crear reportes visuales
```

## 💾 Guardar el Notebook

El archivo `.ipynb` se guarda automáticamente. Puedes:

```bash
# Ver el contenido (es un JSON)
cat mi_primer_notebook.ipynb

# Convertir a HTML para compartir
jupyter nbconvert --to html mi_primer_notebook.ipynb
```

## 📊 Resultado Final

Tu notebook debería verse así:

```
┌──────────────────────────────────────┐
│ mi_primer_notebook.ipynb             │
├──────────────────────────────────────┤
│ [1] import pandas...                 │ → ✓ Librerías...
├──────────────────────────────────────┤
│ [2] data = { ... }                   │ → Tabla HTML
├──────────────────────────────────────┤
│ [3] df.info()                        │ → Output de info
├──────────────────────────────────────┤
│ [4] df[df['edad'] > 28]             │ → Tabla filtrada
├──────────────────────────────────────┤
│ [5] df.groupby(...)                 │ → Series resultado
├──────────────────────────────────────┤
│ [6] plt.bar(...)                    │ → Gráfico
├──────────────────────────────────────┤
│ # Análisis Completado ✓              │ ← Markdown
└──────────────────────────────────────┘
```

## 🎓 Buenas Prácticas Iniciales

✅ Ejecuta celdas de arriba hacia abajo  
✅ Una idea principal por celda  
✅ Usa celdas Markdown para documentar  
✅ Guarda frecuentemente (Ctrl+S)  
✅ Si hay error, usa Restart Kernel y reejecutar  

## 🚀 Próximos Pasos

- Continúa con [Conceptos Clave](../03-conceptos-clave/01-funciones.md)
- Aprende sobre [Limpieza de Datos](../04-flujo-trabajo/02-limpieza-datos.md)
- Practica con [Ejercicios](../06-ejercicios/)

---

¡Felicidades! 🎉 Ya tienes tu primer notebook funcionando.
