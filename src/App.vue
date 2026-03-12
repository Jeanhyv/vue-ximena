<script setup>
import { ref } from 'vue'

// Lógica para el cambio de color de fondo
const modoNoche = ref(false)
const toggleFondo = () => {
  modoNoche.value = !modoNoche.value
}

// Funciones para los modales (Versión Vue)
const abrirModal = (id) => {
  const modal = document.getElementById(id)
  if (modal) modal.style.display = "flex"
}

const cerrarModal = (id) => {
  const modal = document.getElementById(id)
  if (modal) modal.style.display = "none"
}
</script>

<template>
  <div :class="['layout-total', { 'dark-mode': modoNoche }]">
    
    <header>
      <div style="display:flex; align-items:center;">
        <a href="https://www.javascript.com/" target="_blank">
          <img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" alt="Logo JS">
        </a>
        <h1>Plataforma Educativa: Aprende JavaScript</h1>
      </div>
    </header>

    <nav>
      <div class="nav-centrada">
        <a href="https://developer.mozilla.org/es/docs/Web/JavaScript" target="_blank">Documentación</a>
        <a href="https://www.w3schools.com/js/" target="_blank">Tutoriales</a>
        <a href="https://codepen.io/pen/">Ejemplos</a>
        <a href="https://www.freecodecamp.org/espanol/learn/javascript-algorithms-and-data-structures/">Ejercicios</a>
        <a href="https://github.com/topics/javascript">Contacto</a>
        
        <button @click="toggleFondo" class="jean-btn">
          {{ modoNoche ? '☀️ Modo Claro' : '🌙 Modo Oscuro' }}
        </button>
      </div>
    </nav>

    <div class="zona-cuerpo">
      <div class="buscador">
        <input type="text" placeholder="Buscar tema...">
        <button class="btn-buscar" @click="alert('Función de búsqueda simulada 😊')">Buscar</button>
      </div>

      <div class="contenedor">
        <div class="lateral">
          <h3>📚 Recursos útiles</h3>
          <div class="enlaces-verdes">
            <a href="https://developer.mozilla.org/es/docs/Web/JavaScript" target="_blank">MDN JavaScript</a>
            <a href="https://www.w3schools.com/js/" target="_blank">W3Schools JS</a>
            <a href="https://www.javascript.com/" target="_blank">Sitio oficial</a>
          </div>
          <h3>💡 Consejos</h3>
          <p>Practica todos los días y usa la consola del navegador para probar tu código.</p>
        </div>

        <div class="contenido">
          <h2>Temas de JavaScript</h2>
          <button class="info" @click="abrirModal('definicion')">¿Qué es JavaScript?</button>
          <button class="info" @click="abrirModal('tipos')">Tipos de Datos</button>
          <button class="info" @click="abrirModal('operadores')">Operadores y Expresiones</button>
          <button class="info" @click="abrirModal('variables')">Variables</button>
          <button class="info" @click="abrirModal('estructura')">Estructuras de Control</button>
          <button class="info" @click="abrirModal('funciones')">Funciones</button>
          <button class="info" @click="abrirModal('objetos')">Objetos, Propiedades y Métodos</button>
          <button class="info" @click="abrirModal('entrada')">Entrada y Salida de Datos</button>
        </div>

        <div class="lateral">
          <h3>🧠 Aprende más</h3>
          <p>JavaScript es el lenguaje del navegador. ¡Con él puedes crear experiencias increíbles!</p>
          <h4>🔗 Enlaces internos</h4>
          <div class="enlaces-verdes">
            <a href="https://es.wikipedia.org/wiki/JavaScript#Historia">Historia del lenguaje</a>
            <a href="https://javascript.info/">Sintaxis básica</a>
            <a href="https://exercism.org/tracks/javascript">Ejercicios prácticos</a>
          </div>
        </div>
      </div>
    </div>

    <footer>
      <p>© 2025 Plataforma Educativa de JavaScript | Desarrollado por Ximena Castro</p>
    </footer>

    <div id="definicion" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('definicion')">&times;</span>
        <h2>¿Qué es JavaScript?</h2>
        <p>JavaScript es un lenguaje de programación que permite crear interactividad en las páginas web. Es utilizado tanto en el lado del cliente (navegador) como en el servidor (Node.js).</p>
      </div>
    </div>

    <div id="tipos" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('tipos')">&times;</span>
        <h2>Tipos de Datos</h2>
        <ul>
          <li>String → texto</li>
          <li>Number → números</li>
          <li>Boolean → verdadero o falso</li>
          <li>Array → listas</li>
          <li>Object → agrupaciones de valores</li>
          <li>Undefined y Null</li>
        </ul>
      </div>
    </div>

    <div id="operadores" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('operadores')">&times;</span>
        <h2>Operadores y Expresiones</h2>
        <p>Operadores matemáticos: <code>+</code>, <code>-</code>, <code>*</code>, <code>/</code><br>
        Operadores de comparación: <code>==</code>, <code>===</code>, <code>!=</code>, <code>&lt;</code>, <code>&gt;</code></p>
      </div>
    </div>

    <div id="variables" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('variables')">&times;</span>
        <h2>Variables</h2>
        <p>Las variables almacenan información. Se declaran con <code>var</code>, <code>let</code> o <code>const</code>.<br>
        Ejemplo: <code>let nombre = "Ximena";</code></p>
      </div>
    </div>

    <div id="estructura" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('estructura')">&times;</span>
        <h2>Estructuras de Control</h2>
        <p>Controlan el flujo del programa: <br>
        <code>if</code>, <code>else</code>, <code>for</code>, <code>while</code>, <code>switch</code>.</p>
      </div>
    </div>

    <div id="funciones" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('funciones')">&times;</span>
        <h2>Funciones</h2>
        <p>Las funciones son bloques de código que realizan tareas específicas.</p>
        <pre><code>function saludar() {
  alert("¡Hola, mundo!");
}</code></pre>
      </div>
    </div>

    <div id="objetos" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('objetos')">&times;</span>
        <h2>Objetos, Propiedades y Métodos</h2>
        <pre><code>let perro = {
  nombre: "Tomás",
  edad: 7,
  ladrar() {
    alert("Guau!");
  }
}</code></pre>
      </div>
    </div>

    <div id="entrada" class="modal">
      <div class="modal-contenido">
        <span class="cerrar" @click="cerrarModal('entrada')">&times;</span>
        <h2>Entrada y Salida de Datos</h2>
        <p><strong>Entrada:</strong> <code>prompt("¿Cómo te llamas?");</code><br>
        <strong>Salida:</strong> <code>alert("Hola mundo");</code> o <code>console.log("Hola");</code></p>
      </div>
    </div>
  </div>
</template>
<style>

</style>