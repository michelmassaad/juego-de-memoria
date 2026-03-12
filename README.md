# 🎮 Juego de Memoria – Practica de Ingeniería de Software

[![HTML5](https://img.shields.io/badge/HTML5-orange?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML) [![CSS3](https://img.shields.io/badge/CSS3-blue?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS) [![JavaScript](https://img.shields.io/badge/JavaScript-yellow?logo=javascript&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/JavaScript) [![Live Demo](https://img.shields.io/badge/🕹️-Live%20Game-blue)](https://michelmassaad.github.io/juego-de-memoria/)

---

## 🧠 Descripción (Elevator Pitch)

Juego de memoria construído desde cero con HTML, CSS y JavaScript puro. Está orientado a demostrar buenas prácticas de ingeniería — separación de responsabilidades, código modular y principios de Clean Code — en una aplicación estática que permite al usuario emparejar cartas y superar varios niveles de dificultad. El despliegue es local: simplemente abre `index.html` en el navegador.

---

## 🏗️ Arquitectura y Decisiones Técnicas

El código está organizado siguiendo una arquitectura de responsabilidades bien definidas:

1. **Modularidad y POO ligera**: Cada archivo JS actúa como un módulo especializado (barajar, temporizador, UI, lógica del juego). No se utiliza un bundler; en su lugar se cargan scripts de forma ordenada en HTML.
2. **Separación de capas**: 
   - *Vista* (`index.html` + `css/estilo.css`): mínimas clases CSS y estructura DOM clara.
   - *Controladores* (`js/*.js`): funciones puras y manejadores DOM que no contienen lógica de negocio.
   - *Modelo* (`variables.js`): almacena el estado global de la partida (nivel, movimientos, cartas descubiertas).
3. **Clean Code**:
   - Nombres descriptivos en variables y funciones.
   - Comentarios justificativos solo cuando el código pudiera ser confuso.
   - Evitación de duplicación: utilidades comunes (p. ej. reinicio de juego) se abstraen en funciones reutilizables.
4. **Escalabilidad**:
   - La capa de niveles (`cambiaNivel.js`, `menuNiveles.js`) permite agregar nuevos desafíos sin alterar la lógica central.
   - Separación de recursos (`imagenes/`, `sonido/`) facilita reemplazar assets sin tocar código.
5. **Patrones aplicados**:
   - *Módulo* (revealing module pattern implícito): cada script expone una API mínima al global (normalmente solo inicializadores).
   - *Observer* (event listeners): la interacción con el DOM se maneja a través de eventos, manteniendo bajo acoplamiento.
6. **Optimización de renderizado**:
   - Manipulaciones DOM agrupadas y uso de `requestAnimationFrame` en animaciones básicas, evitando reflujo innecesario.

Esta organización facilita la auditoría, pruebas manuales y futuras migraciones(a un framework ligero o aplicación mobile) sin reescribir la lógica.

---

## 🚀 Características Principales

- Niveles de dificultad configurables
- Temporizador con control de tiempo y movimientos
- Sistema de barajado aleatorio garantizando pares
- Recuento de movimientos y notificaciones de acierto/error
- Sonidos e imágenes personalizables
- Código sin frameworks; solo JavaScript ES6 modular
- Estructura apta para ampliar con puntuaciones, almacenamiento local o juego en red

---

## 🛠️ Stack Tecnológico

| Capa       | Tecnologías                              |
|------------|------------------------------------------|
| Frontend   | HTML5, CSS3, JavaScript (ES6)            |
| Herramientas| Ninguna: ejecución local, sin build      |

---

## 🧩 Instalación y Uso Local

```bash
# clona el repositorio
git clone https://github.com/<tu_usuario>/practica-juego-memoria.git
cd practica-juego-memoria

# abre el juego en navegador (no requiere servidor)
# desde Windows
start index.html
# desde macOS/Linux
open index.html
```

Para desarrollo, modifica cualquier archivo JS/CSS y recarga el navegador. No hay dependencias ni pasos de build.

---

## 🧑‍💻 Autor

Michel Massaad – Software Developer

- GitHub: [https://github.com/michel-massaad](https://github.com/michel-massaad)
- LinkedIn: [https://linkedin.com/in/michel-massaad](https://linkedin.com/in/michel-massaad)

---

> Proyecto de práctica personal. Código liberado para uso educativo y revisiones técnicas. Mantén el rigor y la limpieza al contribuir.
