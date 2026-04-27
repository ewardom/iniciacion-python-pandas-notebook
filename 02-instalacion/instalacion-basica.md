# Instalación Básica

Configuración completa del entorno para trabajar con Python, Pandas y Jupyter Notebooks.

## 📋 Requisitos Previos

- Tener **Python 3.8+** instalado
- Acceso a terminal/línea de comandos
- Conexión a internet (para descargar paquetes)

## 🔍 Verificar tu Versión de Python

Verifica que tienes Python instalado:

```bash
python --version
# o
python3 --version
```

Deberías ver algo como: `Python 3.9.x` o superior.

## 📦 Instalación de Dependencias

### Opción 1: Con pip (Recomendado)

```bash
pip install pandas numpy matplotlib seaborn jupyter ipykernel
```

### Opción 2: Instalar desde archivo requirements.txt

Si clonas el repositorio, simplemente ejecuta:

```bash
pip install -r requirements.txt
```

### Opción 3: Con Anaconda (Incluye Todo)

Si prefieres una solución todo-en-uno:

1. Descarga [Anaconda](https://www.anaconda.com/products/individual)
2. Sigue el instalador
3. Anaconda incluye: Python, Jupyter, Pandas, NumPy, Matplotlib, y más

## ✅ Verificar la Instalación

Verifica que todo se instaló correctamente:

```bash
# Verificar pandas
python -c "import pandas; print(f'Pandas {pandas.__version__}')"

# Verificar numpy
python -c "import numpy; print(f'NumPy {numpy.__version__}')"

# Verificar jupyter
jupyter --version

# Verificar matplotlib
python -c "import matplotlib; print(f'Matplotlib {matplotlib.__version__}')"
```

## 🐍 Crear un Entorno Virtual (Recomendado)

Para evitar conflictos de versiones, crea un entorno virtual:

```bash
# Crear el entorno
python -m venv venv

# Activar el entorno
# En macOS/Linux:
source venv/bin/activate

# En Windows:
venv\Scripts\activate
```

Una vez activado, verás `(venv)` en tu terminal.

Luego instala las dependencias:

```bash
pip install -r requirements.txt
```

## 🚀 Primeros Pasos

### Test Rápido en Python

```bash
python
```

Dentro de Python:

```python
import pandas as pd
import numpy as np

# Crear un DataFrame simple
df = pd.DataFrame({
    'nombre': ['Juan', 'María'],
    'edad': [25, 30]
})

print(df)
exit()
```

Deberías ver tu DataFrame impreso. ✅

---

**Siguiente:** [Instalación de VS Code →](vs-code-setup.md)
