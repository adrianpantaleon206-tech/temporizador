# 🚀 Inicio de Despegue - Cuenta Regresiva Espacial

Una aplicación web interactiva y futurista con temática espacial, desarrollada con **HTML5**, **CSS3** (diseño Cyberpunk/Neón) y **JavaScript vainilla**. Cuenta con un temporizador de cuenta regresiva, efectos visuales de estrellas parpadeantes, luces LED laterales, animación de lanzamiento de un cohete y una explosión de partículas de colores al finalizar el conteo.

---

## ✨ Características Principales

- **Pantalla Inmersiva Estelar**: Fondo oscuro con animación aleatoria de estrellas parpadeantes.
- **Diseño Cyberpunk / Sci-Fi**: Tarjeta de control futurista con bordes de neón y luces LED intermitentes en los laterales.
- **Números Fosforescentes**: Dígitos gigantes en color naranja neón (`#ff5500`) con múltiples capas de efecto *glow* (resplandor).
- **Control de Tiempo Preciso**: Temporizador robusto configurable que descuenta segundo a segundo sin errores de sincronización.
- **Validación con Expresiones Regulares (RegEx)**: Implementación de patrones en JavaScript para el formateo de dígitos a formato estándar `MM:SS`.
- **Secuencia de Lanzamiento**: Al llegar a `00:00`, se oculta el temporizador, aparece un cohete despegando con animación dinámica y se activa una explosión de partículas multicolores.
- **Controles Interactivos**: Botones de **DESPEGAR** (bloqueado durante la ejecución) y **REINICIAR** (restablece el estado inicial).

---

## 🛠️ Tecnologías Utilizadas

- **HTML5**: Estructura semántica de la interfaz.
- **CSS3**: Variables CSS (`:root`), Flexbox, animaciones personalizadas con `@keyframes` y efectos de desenfoque (`backdrop-filter`).
- **JavaScript (ES6+)**: Manipulación del DOM, gestión de intervalos (`setInterval`) y expresiones regulares (`RegEx`).

---

## 📁 Estructura del Proyecto

Puedes estructurarlo de dos formas:

### Opción A: Archivo único (Recomendado para pruebas rápidas)
- `index.html` (Contiene la estructura, estilos y lógica juntos para garantizar ejecución inmediata).

### Opción B: Archivos separados
- `index.html` — Estructura HTML y estilos CSS.
- `script.js` — Lógica del temporizador, animaciones y partículas.

---

## 🚀 Cómo Ejecutar el Proyecto

1. Clona o descarga este repositorio en tu computadora.
2. Asegúrate de tener los archivos guardados en una misma carpeta.
3. Haz doble clic en el archivo **`index.html`** para abrirlo en cualquier navegador web moderno (Google Chrome, Firefox, Edge, Safari).
4. Haz clic en el botón **DESPEGAR** para iniciar la cuenta regresiva.

---

## 📝 Fragmento Destacado (Uso de RegEx)

El proyecto utiliza expresiones regulares para asegurar que los minutos y segundos mantengan siempre el formato de dos dígitos (`00:00`):

```javascript
function formatTimeWithRegex(totalSeconds) {
  const mins = Math.floor(totalSeconds / 60);
  const secs = totalSeconds % 60;

  // Reemplaza un único dígito aislado añadiendo un '0' a la izquierda
  const formattedMins = String(mins).replace(/^(\d)$/, '0$1');
  const formattedSecs = String(secs).replace(/^(\d)$/, '0$1');

  return `${formattedMins}:${formattedSecs}`;
}
