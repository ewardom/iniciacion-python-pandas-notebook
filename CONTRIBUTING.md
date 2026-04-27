# Contribuyendo a esta Guía

¡Gracias por tu interés en mejorar esta guía de Python, Pandas y Jupyter! 

## 🤝 ¿Cómo Contribuir?

Hay varias formas de ayudar:

### 1. Reportar Errores 🐛

Si encuentras un error, typo o información inexacta:

1. Abre un **Issue** en GitHub
2. Describe el problema claramente
3. Incluye dónde se encuentra (archivo y línea si es posible)
4. Proporciona un ejemplo si es relevante

**Ejemplo:**
```
Título: Error en el ejemplo de groupby en sección 4-flujo-trabajo

Descripción: El ejemplo de groupby en la página XX produjo un error cuando lo ejecuté porque...
```

### 2. Sugerir Mejoras 💡

¿Tienes una idea para mejorar la guía?

1. Abre un **Issue** con la etiqueta `enhancement`
2. Explica la mejora propuesta
3. Explica por qué crees que sería útil

### 3. Agregar Contenido 📝

¿Quieres agregar ejercicios, ejemplos o secciones nuevas?

1. **Fork** el repositorio
2. **Crea una rama**: `git checkout -b feature/nuevo-contenido`
3. Escribe el contenido
4. Asegúrate de seguir el [Estilo de la Guía](#estilo-de-la-guía)
5. **Commit**: `git commit -m "Añade nuevo contenido sobre X"`
6. **Push**: `git push origin feature/nuevo-contenido`
7. Abre un **Pull Request**

### 4. Mejorar Ejemplos 🔧

Si encontraste una forma mejor de explicar algo:

1. Edita el archivo
2. Mantén la misma estructura
3. Verifica que tu código funcione
4. Abre un PR con la mejora

---

## 📋 Estilo de la Guía

Para mantener consistencia, por favor sigue estos estilos:

### Títulos

```markdown
# Título Principal (Sección)
## Subtítulo (Tema)
### Sub-subtítulo (Concepto)
```

### Emojis

Usamos emojis consistentemente:

- 🎯 Objetivos
- ✅ Buenas prácticas / Bien
- ❌ Malas prácticas / Mal
- 📝 Notas importantes
- 💡 Tips y trucos
- 🐛 Errores comunes
- 📚 Recursos
- 🚀 Quick starts

### Bloques de Código

```python
# ✅ Bien
resultado = df[df['edad'] > 25]

# ❌ Mal
resultado = df(df['edad'] > 25)  # Error de sintaxis
```

### Estructura de Archivos

```markdown
# Título

Una breve introducción (1-2 líneas).

## Sección 1
Contenido...

## Sección 2
Contenido...

### Subsección
Más detalles...

---

**Siguiente:** [Siguiente sección →](enlace-relativo.md)
```

---

## ✨ Checklist para Contribuciones

- [ ] El contenido es exacto y está probado
- [ ] El código fue ejecutado y funciona
- [ ] Sigue el estilo de la guía
- [ ] Incluye ejemplos cuando es apropiado
- [ ] Está dirigido al nivel correcto (básico/intermedio/avanzado)
- [ ] Los enlaces internos funcionan
- [ ] He revisado el contenido para errores

---

## 📝 Proceso de Pull Request

1. **Fork** el repositorio
2. Crea una rama con un nombre descriptivo
3. Haz tus cambios
4. **Commit** con mensajes claros:
   - `git commit -m "Agrega ejemplos de groupby"`
   - `git commit -m "Corrige typo en sección de filtrado"`
   - `git commit -m "Mejora explicación de DataFrames"`
5. **Push** a tu fork
6. Abre un Pull Request con:
   - Título claro
   - Descripción de qué cambió
   - Por qué debería mergearse

**Ejemplo de PR:**
```
Título: Añade sección sobre variables globales en funciones

Descripción:
- Agrega explicación sobre scope de variables
- Incluye 3 ejemplos prácticos
- Explica errores comunes

Relacionado con: #42 (si es relevante)
```

---

## 🏗️ Directrices por Tipo de Contribución

### Agregar Ejercicios

- [ ] Incluir enunciado claro
- [ ] Proporcionar datos de ejemplo o enlace a datos
- [ ] En carpeta `06-ejercicios/`
- [ ] Incluir solución en `soluciones/`
- [ ] Nivel de dificultad indicado (básico/intermedio/avanzado)

### Agregar Ejemplos

- [ ] Código verificado y funcional
- [ ] Explicación clara de qué hace
- [ ] Alternativas (si existen)
- [ ] Output esperado mostrado

### Corregir Errores

- [ ] Describe el error
- [ ] Proporciona la corrección
- [ ] Explica por qué era un error
- [ ] Verifica que no hayas introducido otros

### Actualizar Recursos

- [ ] Verifica que los enlaces funcionen
- [ ] Actualiza descripciones si es necesario
- [ ] Mantén el formato consistente
- [ ] Agrupa por categoría

---

## 🚫 Lo Que NO Hacemos

- ❌ Contenido fuera del scope (ej: tutoriales de JavaScript)
- ❌ Autopromoción o spam
- ❌ Contenido ofensivo o discriminatorio
- ❌ Duplicación de contenido existente sin valor agregado

---

## 👥 Código de Conducta

Nos comprometemos a mantener un ambiente respetuoso y acogedor:

- 🤝 Sé respetuoso con otros
- 💬 Comunica de forma clara y constructiva
- 📚 Acepta crítica constructiva
- 🙅‍♂️ No discriminación de ningún tipo

---

## ❓ Preguntas Frecuentes

**P: ¿Necesito experiencia para contribuir?**  
A: ¡No! Todas las contribuciones son bienvenidas, desde principiantes.

**P: ¿Cuánto tiempo toma que revisen mi PR?**  
A: Generalmente 1-2 semanas, dependiendo de la complejidad.

**P: ¿Puedo traducir a otro idioma?**  
A: Sí, por favor crea un nuevo repositorio o rama para ello.

**P: ¿Hay compensación?**  
A: Este es un proyecto de código abierto. La recompensa es el impacto en la comunidad.

---

## 📞 Contacto

- **Issues** — Para reportes y sugerencias
- **Pull Requests** — Para contribuciones de código
- **Discussions** — Para preguntas generales

---

**¡Gracias por hacer esta guía mejor para todos! 🙏**

---

<div align="center">

**Hecho con ❤️ para la comunidad de Python**

</div>
