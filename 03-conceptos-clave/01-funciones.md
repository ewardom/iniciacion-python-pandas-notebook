# Funciones: DRY (Don't Repeat Yourself)

Principio fundamental: Si repites código, crea una función.

## 🎯 ¿Por Qué Crear Funciones?

- ✅ **Reutilización:** Escribe una vez, usa muchas veces
- ✅ **Mantenimiento:** Cambios en un único lugar
- ✅ **Legibilidad:** Código más limpio y ordenado
- ✅ **Testing:** Fácil de probar
- ✅ **Eficiencia:** Evita errores por copiar-pegar

## ❌ Ejemplo Malo (Sin Funciones)

```python
# Repetir código múltiples veces
resultado1 = datos1 * 2
resultado2 = datos2 * 2
resultado3 = datos3 * 2
resultado4 = datos4 * 2

promedio1 = sum(datos1) / len(datos1)
promedio2 = sum(datos2) / len(datos2)
promedio3 = sum(datos3) / len(datos3)
```

**Problemas:**
- 😫 Código repetido
- 🐛 Error al copiar = error en todos lados
- 📝 Difícil de mantener

## ✅ Ejemplo Bueno (Con Funciones)

```python
def multiplicar_por_dos(datos):
    """Multiplica cada elemento por 2"""
    return datos * 2

def calcular_promedio(datos):
    """Calcula el promedio de una lista"""
    return sum(datos) / len(datos)

# Usar las funciones
resultado1 = multiplicar_por_dos(datos1)
resultado2 = multiplicar_por_dos(datos2)
resultado3 = multiplicar_por_dos(datos3)

promedio1 = calcular_promedio(datos1)
promedio2 = calcular_promedio(datos2)
```

**Ventajas:**
- ✅ Código limpio
- ✅ Un cambio, se aplica a todo
- ✅ Fácil de entender

## 📚 Anatomía de una Función

```python
def nombre_funcion(parametro1, parametro2, parametro3=valor_defecto):
    """
    Esto es un docstring: describe qué hace la función
    
    Args:
        parametro1: Descripción
        parametro2: Descripción
        parametro3: Descripción (opcional, tiene valor por defecto)
        
    Returns:
        type: Descripción del valor retornado
    """
    # Cuerpo de la función
    resultado = parametro1 + parametro2
    return resultado
```

### Partes:
1. **`def`** — Declara la función
2. **Nombre** — Descriptivo y en minúsculas
3. **Parámetros** — Inputs de la función
4. **Docstring** — Documentación
5. **Código** — La lógica
6. **`return`** — Lo que devuelve

## 💡 Ejemplos Prácticos

### Función Simple

```python
def saludar(nombre):
    """Saluda a alguien por su nombre"""
    return f"¡Hola, {nombre}!"

# Uso
print(saludar("Juan"))  # ¡Hola, Juan!
print(saludar("María")) # ¡Hola, María!
```

### Función con Múltiples Parámetros

```python
def calcular_imc(peso_kg, altura_m):
    """
    Calcula el Índice de Masa Corporal
    
    Args:
        peso_kg: Peso en kilogramos
        altura_m: Altura en metros
        
    Returns:
        float: El IMC
    """
    imc = peso_kg / (altura_m ** 2)
    return round(imc, 2)

# Uso
print(calcular_imc(70, 1.75))  # 22.86
print(calcular_imc(80, 1.80))  # 24.69
```

### Función con Parámetro por Defecto

```python
def aplicar_descuento(precio, descuento=0.1):
    """
    Aplica un descuento a un precio
    
    Args:
        precio: Precio original
        descuento: Porcentaje de descuento (0.1 = 10%, por defecto)
        
    Returns:
        float: Precio final con descuento
    """
    return precio * (1 - descuento)

# Uso
print(aplicar_descuento(100))          # 90.0 (10% por defecto)
print(aplicar_descuento(100, 0.15))    # 85.0 (15%)
print(aplicar_descuento(100, 0.20))    # 80.0 (20%)
```

### Función que Retorna Múltiples Valores

```python
def estadisticas(datos):
    """Calcula mín, máx y promedio"""
    minimo = min(datos)
    maximo = max(datos)
    promedio = sum(datos) / len(datos)
    return minimo, maximo, promedio

# Uso
min_val, max_val, prom = estadisticas([10, 20, 30, 40, 50])
print(f"Mín: {min_val}, Máx: {max_val}, Promedio: {prom}")
# Mín: 10, Máx: 50, Promedio: 30
```

## 🔧 Funciones útiles para Pandas

### Procesar una Columna Completa

```python
def procesar_nombre(nombre):
    """Convierte nombre a mayúscula y elimina espacios"""
    return nombre.strip().upper()

# Usar con DataFrame
df['nombre'] = df['nombre'].apply(procesar_nombre)
```

### Crear Categorías

```python
def categorizar_edad(edad):
    """Categoriza edad en grupos"""
    if edad < 18:
        return 'Menor'
    elif edad < 65:
        return 'Adulto'
    else:
        return 'Mayor'

# Usar con DataFrame
df['categoria_edad'] = df['edad'].apply(categorizar_edad)
```

## 📋 Checklist para Escribir Buenas Funciones

✅ **Nombre descriptivo** — `calcular_promedio` ✓, `calc_prom` ✗  
✅ **Una responsabilidad** — La función hace UNA cosa bien  
✅ **Docstring claro** — Alguien ajeno entiende qué hace  
✅ **Parámetros lógicos** — Nombres significativos  
✅ **Manejo de errores** — ¿Qué pasa si los datos están mal?  
✅ **Testeable** — Fácil de probar  

## 🚫 Errores Comunes

### ❌ Función muy compleja

```python
def hacer_todo(datos):  # ¡MAL!
    # 50 líneas de código
    # Hace muchas cosas
    pass
```

**Solución:** Dividir en funciones más pequeñas.

### ❌ Nombre poco descriptivo

```python
def f(x):  # ¿Qué hace esto?
    return x * 2
```

**Solución:** `def multiplicar_por_dos(numero):`

### ❌ Sin documentación

```python
def proc(d, v):  # ¿Qué son d y v?
    return d + v
```

**Solución:** Agregar docstring.

---

**Siguiente:** [Series y DataFrames →](02-pandas-series.md)
