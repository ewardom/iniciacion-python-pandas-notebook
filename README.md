# 📊 Python, Pandas y Jupyter Notebooks - Guía Completa

> Una guía práctica y moderna para dominar el análisis de datos con Python. Desde conceptos básicos hasta workflows profesionales.

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Latest-darkgreen?logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 🎯 ¿Qué encontrarás aquí?

Esta guía está diseñada para ayudarte a:
- ✅ Entender los fundamentos de Jupyter Notebooks
- ✅ Instalar y configurar tu entorno en VS Code
- ✅ Dominar Pandas para análisis de datos
- ✅ Aprender buenas prácticas profesionales
- ✅ Crear notebooks eficientes y documentados

---

## 📚 Tabla de Contenidos

### 1. [Introducción](./01-introduccion/)
- ¿Qué es Jupyter Notebook?
- Características principales
- Ventajas para análisis de datos

### 2. [Instalación](./02-instalacion/)
- Configuración del entorno
- Instalación de dependencias
- Instalación de extensión Jupyter en VS Code
- Primeros pasos

### 3. [Conceptos Clave](./03-conceptos-clave/)
- Funciones: DRY (Don't Repeat Yourself)
- Pandas como librería principal
- Series vs DataFrames
- Métodos útiles de Pandas

### 4. [Flujo de Trabajo con Pandas](./04-flujo-trabajo/)
- Lectura y escritura de datos
- Limpieza de datos
- Transformación y agregación
- Merges y Joins
- Visualización de resultados

### 5. [Buenas Prácticas](./05-buenas-practicas/)
- Mejores prácticas en Jupyter
- Mejores prácticas en Python/Pandas
- Estructura de un notebook
- Tips y tricks

### 6. [Ejercicios Prácticos](./06-ejercicios/)
- Ejercicios progresivos
- Proyectos integradores
- Soluciones comentadas

### 7. [Recursos](./07-recursos/)
- Enlaces útiles
- Documentación oficial
- Datasets para practicar

---

## 📋 Estructura del Repositorio

```
python-pandas-jupyter/
├── README.md                      # Este archivo
├── requirements.txt               # Dependencias del proyecto
├── .gitignore                    # Archivos ignorados por git
│
├── 01-introduccion/
│   ├── que-es-jupyter.md
│   ├── caracteristicas.md
│   └── ventajas.md
│
├── 02-instalacion/
│   ├── instalacion-basica.md
│   ├── vs-code-setup.md
│   └── primeros-pasos.md
│
├── 03-conceptos-clave/
│   ├── 01-funciones.md
│   ├── 02-pandas-series.md
│   ├── 03-pandas-dataframe.md
│   └── 04-metodos-utiles.md
│
├── 04-flujo-trabajo/
│   ├── 01-lectura-escritura.md
│   ├── 02-limpieza-datos.md
│   ├── 03-transformacion.md
│   ├── 04-merges-joins.md
│   └── 05-visualizacion.md
│
├── 05-buenas-practicas/
│   ├── notebooks.md
│   ├── python-pandas.md
│   └── estructura-tipica.md
│
├── 06-ejercicios/
│   ├── 01-basico/
│   ├── 02-intermedio/
│   ├── 03-avanzado/
│   └── soluciones/
│
└── 07-recursos/
    ├── enlaces-utiles.md
    └── datasets.md
```

---

## 💻 Requisitos Previos

- **Python 3.8+** instalado
- **VS Code** (opcional pero recomendado)
- Conocimientos básicos de Python
- Disposición para aprender 🎓

---

## 📦 Dependencias

Las dependencias principales están en `requirements.txt`:

```
pandas>=1.3.0
numpy>=1.21.0
jupyter>=1.0.0
matplotlib>=3.4.0
seaborn>=0.11.0
```

Instálalas con:
```bash
pip install -r requirements.txt
```

---

## 🎓 Cómo Usar Esta Guía

### Para Principiantes
1. Comienza con la [Introducción](./01-introduccion/)
2. Sigue la [Instalación](./02-instalacion/)
3. Aprende los [Conceptos Clave](./03-conceptos-clave/)
4. Realiza los [Ejercicios Básicos](./06-ejercicios/01-basico/)

### Para Usuarios Intermedios
1. Revisa el [Flujo de Trabajo](./04-flujo-trabajo/)
2. Estudia [Buenas Prácticas](./05-buenas-practicas/)
3. Intenta los [Ejercicios Intermedios](./06-ejercicios/02-intermedio/)

### Para Usuarios Avanzados
1. Consulta los [Ejercicios Avanzados](./06-ejercicios/03-avanzado/)
2. Explora los [Recursos](./07-recursos/) para profundizar
3. Crea tus propios notebooks

---

## 🔍 Ejemplos Rápidos

### Crear un DataFrame
```python
import pandas as pd

df = pd.DataFrame({
    'nombre': ['Juan', 'María', 'Carlos'],
    'edad': [25, 30, 28],
    'ciudad': ['Madrid', 'Barcelona', 'Valencia']
})

print(df)
```

### Filtrar datos
```python
# Obtener personas mayores de 25 años
df[df['edad'] > 25]
```

### Agrupar y agregar
```python
# Promedio de edad por ciudad
df.groupby('ciudad')['edad'].mean()
```

### Crear visualizaciones
```python
import matplotlib.pyplot as plt

df['ciudad'].value_counts().plot(kind='bar', title='Cantidad por ciudad')
plt.show()
```

---

## 🤝 Contribuciones

¿Encontraste un error? ¿Tienes mejoras?

1. Fork el repositorio
2. Crea una rama: `git checkout -b feature/mejora`
3. Commit tus cambios: `git commit -m 'Añade mejora'`
4. Push a la rama: `git push origin feature/mejora`
5. Abre un Pull Request

---

## 📖 Recursos Adicionales

- [Documentación oficial de Pandas](https://pandas.pydata.org/docs/)
- [Documentación oficial de Jupyter](https://jupyter.org/)
- [Cheat Sheet de Pandas](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
- [Kaggle Datasets](https://www.kaggle.com/datasets)
- [Stack Overflow - Pandas Tag](https://stackoverflow.com/questions/tagged/pandas)

---

## 📝 Licencia

Este proyecto está bajo la licencia MIT. Ver [LICENSE](LICENSE) para más detalles.

---

## 📞 Contacto y Soporte

Si tienes preguntas:
- 📧 Abre un **Issue** en GitHub
- 💬 Consulta la **Documentación**
- 🔗 Revisa los **Recursos** del proyecto

---

## ⭐ ¿Te Gustó?

Si este repositorio te fue útil, no olvides darle una ⭐ en GitHub para apoyar el proyecto.

---

<div align="center">

**¡Bienvenido al mundo del análisis de datos con Python! 🚀**

Hecho con ❤️ para la comunidad Python

</div>
