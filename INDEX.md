# Índice Completo de la Guía

## 📂 Estructura del Repositorio

```
python-pandas-jupyter/
├── README.md                              ← COMIENZA AQUÍ
├── INDEX.md                               ← Este archivo
├── requirements.txt                       ← Dependencias
├── .gitignore                             ← Archivos ignorados
│
├── 01-introduccion/
│   ├── que-es-jupyter.md                 ← ¿Qué es Jupyter?
│   ├── caracteristicas.md                ← Características
│   └── ventajas.md                       ← Ventajas para análisis
│
├── 02-instalacion/
│   ├── instalacion-basica.md             ← Dependencias Python
│   ├── vs-code-setup.md                  ← Jupyter en VS Code
│   └── primeros-pasos.md                 ← Tu primer notebook
│
├── 03-conceptos-clave/
│   ├── 01-funciones.md                   ← DRY (Don't Repeat)
│   ├── 02-pandas-series.md               ← Series y DataFrames
│   ├── 04-metodos-utiles.md              ← Top 10 métodos
│   └── README.md                         ← Resumen conceptos
│
├── 04-flujo-trabajo/
│   ├── 01-lectura-escritura.md           ← CSV, Excel, JSON
│   ├── 02-limpieza-datos.md              ← Valores nulos, tipos
│   ├── 03-transformacion.md              ← groupby, merge
│   ├── 04-merges-joins.md                ← Combinar datos
│   ├── 05-visualizacion.md               ← Gráficos con matplotlib
│   └── README.md                         ← Resumen workflow
│
├── 05-buenas-practicas/
│   ├── notebooks.md                      ← En Jupyter
│   ├── python-pandas.md                  ├── En Python/Pandas
│   ├── estructura-tipica.md              ├── Estructura notebook
│   └── README.md                         ├── Resumen prácticas
│
├── 06-ejercicios/
│   ├── 01-basico/
│   │   ├── ejercicio-1.md                ├── Crear DataFrame
│   │   ├── ejercicio-2.md                ├── Filtrar datos
│   │   ├── ejercicio-3.md                ├── Estadísticas
│   │   └── soluciones/
│   │
│   ├── 02-intermedio/
│   │   ├── ejercicio-1.md                ├── Limpieza de datos
│   │   ├── ejercicio-2.md                ├── Agrupación
│   │   └── soluciones/
│   │
│   ├── 03-avanzado/
│   │   ├── proyecto-final.md             ├── Proyecto integrador
│   │   └── soluciones/
│   │
│   └── README.md                         ← Guía de ejercicios
│
└── 07-recursos/
    ├── enlaces-utiles.md                 ← Documentación
    ├── datasets.md                       ← Dónde encontrar datos
    ├── cheatsheets.md                    ├── Resúmenes
    └── README.md                         ├── Resumen recursos
```

---

## 🎯 Camino de Aprendizaje

### Para Principiantes (1-2 semanas)

**Semana 1:**
- [ ] [¿Qué es Jupyter?](01-introduccion/que-es-jupyter.md) — 15 min
- [ ] [Instalación Básica](02-instalacion/instalacion-basica.md) — 30 min
- [ ] [Setup en VS Code](02-instalacion/vs-code-setup.md) — 20 min
- [ ] [Primeros Pasos](02-instalacion/primeros-pasos.md) — 30 min

**Semana 2:**
- [ ] [Funciones](03-conceptos-clave/01-funciones.md) — 1 hora
- [ ] [Series y DataFrames](03-conceptos-clave/02-pandas-series.md) — 1.5 horas
- [ ] [Métodos Útiles](03-conceptos-clave/04-metodos-utiles.md) — 1 hora
- [ ] Resolver [Ejercicios Básicos](06-ejercicios/01-basico/) — 2 horas

**Tiempo total:** ~8 horas

---

### Para Usuarios Intermedios (2-3 semanas)

**Semana 1-2:**
- [ ] Review [Conceptos Clave](03-conceptos-clave/) — 2 horas
- [ ] [Lectura/Escritura](04-flujo-trabajo/01-lectura-escritura.md) — 1 hora
- [ ] [Limpieza de Datos](04-flujo-trabajo/02-limpieza-datos.md) — 1.5 horas
- [ ] [Transformación](04-flujo-trabajo/03-transformacion.md) — 1.5 horas

**Semana 3:**
- [ ] [Merges y Joins](04-flujo-trabajo/04-merges-joins.md) — 1 hora
- [ ] [Visualización](04-flujo-trabajo/05-visualizacion.md) — 1 hora
- [ ] Resolver [Ejercicios Intermedios](06-ejercicios/02-intermedio/) — 3 horas

**Tiempo total:** ~12 horas

---

### Para Usuarios Avanzados (1-2 semanas)

- [ ] Review [Buenas Prácticas](05-buenas-practicas/)
- [ ] [Proyecto Final](06-ejercicios/03-avanzado/proyecto-final.md) — 5-8 horas
- [ ] Consultar [Recursos Avanzados](07-recursos/)

**Tiempo total:** ~10 horas

---

## 🚀 Quick Reference

### Métodos más usados

```python
df.head()                    # Ver primeras filas
df.info()                    # Información
df.describe()                # Estadísticas
df['col'].value_counts()     # Contar valores
df[df['col'] > 5]            # Filtrar
df.groupby('col').mean()     # Agrupar
df.fillna(0)                 # Llenar nulos
df.sort_values('col')        # Ordenar
```

### Atajos de teclado (VS Code)

```
Shift+Enter    → Ejecutar celda
Ctrl+/         → Comentar línea
Cmd+Shift+P    → Paleta de comandos
Ctrl+H         → Buscar y reemplazar
```

---

## 📞 Navegación Rápida

| Necesito... | Ir a... |
|-----------|---------|
| Empezar desde cero | [README.md](README.md) |
| Instalar todo | [Instalación Básica](02-instalacion/instalacion-basica.md) |
| Aprender Pandas | [Conceptos Clave](03-conceptos-clave/) |
| Crear reportes | [Buenas Prácticas](05-buenas-practicas/) |
| Practicar | [Ejercicios](06-ejercicios/) |
| Más recursos | [Recursos](07-recursos/) |

---

## ✅ Checklist de Progreso

### Fundamentos
- [ ] Entiendo qué es Jupyter Notebook
- [ ] Tengo todo instalado y funcionando
- [ ] Puedo crear y ejecutar notebooks
- [ ] Entiendo Series y DataFrames

### Intermedio
- [ ] Puedo limpiar datos
- [ ] Puedo hacer groupby y agregaciones
- [ ] Puedo hacer merges
- [ ] Puedo crear visualizaciones

### Avanzado
- [ ] Sigo buenas prácticas
- [ ] Puedo hacer un análisis completo
- [ ] Puedo crear reportes profesionales
- [ ] Entiendo el flujo end-to-end

---

**¡Bienvenido a tu viaje en análisis de datos! 🚀**

---

<div align="center">

**Última actualización:** Abril 2026

Hecho con ❤️ para la comunidad de análisis de datos

</div>
