# Instalación de Jupyter en VS Code

Configura Jupyter Notebook directamente en VS Code para una experiencia integral.

## 🎯 ¿Por Qué Usar Jupyter en VS Code?

✅ Todo en un solo lugar (código + notebooks + terminal)  
✅ Mejor experiencia de desarrollo  
✅ Integración con Git  
✅ Temas personalizables  
✅ Sin necesidad de abrir navegador  

## 📦 Extensión Oficial de Jupyter

### Opción 1: Desde la Interfaz de VS Code

1. **Abre VS Code**
2. Ve a **Extensiones** (icono de 4 cuadrados en la barra lateral o `Cmd+Shift+X` en Mac / `Ctrl+Shift+X` en Windows/Linux)
3. Busca **"Jupyter"** en la barra de búsqueda
4. Haz clic en la extensión oficial **"Jupyter"** de Microsoft
5. Presiona el botón **"Install"** (Instalar)

### Opción 2: Desde Terminal

```bash
code --install-extension ms-toolsai.jupyter
```

### Opción 3: Instalar Jupyter Kernel

Para que Jupyter use tu entorno con los paquetes instalados:

```bash
python -m ipykernel install --user --name python3
```

## 🚀 Usar Jupyter Notebooks en VS Code

### Crear un Nuevo Notebook

1. **Método 1:** Crea un archivo con extensión `.ipynb`
   ```bash
   touch mi_analisis.ipynb
   ```

2. **Método 2:** En VS Code
   - `Ctrl+Shift+P` (o `Cmd+Shift+P` en Mac)
   - Escribe: "Create: New Jupyter Notebook"
   - Presiona Enter

3. **Método 3:** Desde la interfaz
   - File → New File → Jupyter Notebook

### Estructura de un Notebook en VS Code

```
┌─────────────────────────────────────┐
│ Mi Análisis de Datos                │ ← Nombre del archivo
├─────────────────────────────────────┤
│ + Code    + Markdown                │ ← Botones para agregar celdas
├─────────────────────────────────────┤
│ [ ] import pandas as pd             │ ← Celda de código
│ [ ] Run | Debug                     │    (botones para ejecutar)
├─────────────────────────────────────┤
│ # Mi primer análisis                │ ← Celda Markdown
├─────────────────────────────────────┤
│ [ ] print("Hola Pandas!")           │ ← Otra celda de código
│ [ ] Run | Debug                     │
└─────────────────────────────────────┘
```

## ⌨️ Atajos de Teclado Útiles

| Atajo | Acción |
|-------|--------|
| `Shift+Enter` | Ejecutar celda y pasar a la siguiente |
| `Ctrl+Enter` | Ejecutar celda sin avanzar |
| `Ctrl+Shift+Enter` | Ejecutar todas las celdas |
| `Ctrl+M + B` | Insertar celda debajo |
| `Ctrl+M + A` | Insertar celda arriba |
| `Ctrl+M + D` | Eliminar celda |
| `Ctrl+M + M` | Convertir a Markdown |
| `Ctrl+M + Y` | Convertir a código |

## 🎨 Temas Personalizados

VS Code permite personalizar la apariencia:

1. Ve a **Archivo → Preferencias → Tema de Color**
2. Busca temas de Jupyter
3. Algunos recomendados:
   - "Jupyter Light"
   - "Jupyter Dark"
   - "Monokai Pro"

## 🔧 Configuración Adicional

### Variables de Python

Puedes usar variables a través de diferentes celdas:

```python
# Celda 1
x = 10
y = 20
```

```python
# Celda 2
print(x + y)  # Output: 30
```

### Limpiar Variables

```python
# Borrar una variable
del x

# Borrar todas las variables
%reset
```

### Comandos Mágicos

```python
# Ver el tiempo de ejecución
%timeit sum(range(1000))

# Ver variables definidas
%whos

# Limpiar salida
%clear

# Mostrar gráficos inline (automático en VS Code)
%matplotlib inline
```

## 🐛 Solucionar Problemas

### El kernel no se inicia
```bash
python -m ipykernel install --user --force-reinstall
```

### Falta la extensión Python
```bash
code --install-extension ms-python.python
```

### Limpiar caché de Jupyter
```bash
rm -rf ~/.jupyter/  # macOS/Linux
del %APPDATA%\.jupyter\  # Windows
```

---

**Siguiente:** [Primeros Pasos →](primeros-pasos.md)
