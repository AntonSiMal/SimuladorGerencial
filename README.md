

# 🏢 Simulador Gerencial: Sistema de Simulación de Decisiones Empresariales

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Sin Dependencias](https://img.shields.io/badge/Sin%20Dependencias-000000?style=for-the-badge)

## 📖 Descripción General
**Simulador Gerencial** es una aplicación web interactiva de una sola página (SPA) diseñada para simular la toma de decisiones directivas a lo largo de un ciclo empresarial de 5 años (60 meses). 

El sistema pone al usuario en el rol de un gerente general que debe equilibrar cinco indicadores clave de rendimiento (KPIs) mientras enfrenta dilemas laborales, imprevistos del entorno y eventos financieros obligatorios. Su arquitectura ligera y su lógica de estado en el cliente lo convierten en una herramienta portátil, rápida y fácil de desplegar en cualquier entorno.

---

## ⚙️ ¿Qué hace la aplicación?
* **Simulación por Turnos:** Gestiona un ciclo de 60 meses, con eventos específicos que se activan en meses clave (ej. mes 5 y mes 12).
* **Gestión de KPIs:** Rastrea y actualiza en tiempo real 5 indicadores: Productividad, Clima Laboral, Presupuesto, Disciplina y Talento (escala de 0 a 10).
* **Banco de Escenarios:** Cuenta con 60 dilemas gerenciales únicos y 60 eventos de "Realidad Organizacional" que se barajan aleatoriamente para garantizar que no se repitan en una misma partida.
* **Sistema de Comodines de Liderazgo:** Otorga al usuario 3 habilidades especiales por año (ej. "Negociación", "Visión Financiera") para mitigar las consecuencias negativas de una decisión antes de que se apliquen.
* **Mecánica de Incertidumbre (Dado del Entorno):** Después de cada decisión, un "dado virtual" determina si el entorno se mantiene estable o si se activa un evento aleatorio inesperado.
* **Bitácora en Tiempo Real:** Registra automáticamente cada decisión, el mes en que se tomó y los comodines utilizados, generando un historial visible para el usuario.
* **Sistema de Retroalimentación:** Al finalizar la partida (ya sea por colapso de un indicador o por completar los 5 años), ofrece un análisis detallado del desempeño, los puntos más bajos alcanzados y la racha máxima de estabilidad.

---

## 🚫 ¿Qué NO hace la aplicación?
* **No requiere Backend:** No hay base de datos, API ni servidor. Toda la lógica y el estado se manejan en el navegador del cliente (Client-Side).
* **No guarda progreso persistente:** Al recargar la página, la partida se reinicia. Está diseñada para sesiones de juego continuas (aprox. 15-20 minutos).
* **No es multijugador:** Es una experiencia en solitario (Single Player) enfocada en la toma de decisiones individual.
* **No utiliza frameworks externos:** No depende de React, Vue, jQuery ni librerías de terceros. Es 100% Vanilla JS, lo que garantiza un rendimiento máximo y cero vulnerabilidades de dependencias.

---

## 🔄 ¿Cómo funciona? (Ciclo de un Turno)
1. **Análisis:** El sistema presenta un dilema gerencial con 3 opciones de respuesta (ordenadas aleatoriamente).
2. **Decisión:** El usuario selecciona una opción. El sistema calcula el impacto base en los 5 KPIs.
3. **Mitigación (Opcional):** Antes de confirmar, el usuario puede activar un "Comodín de Liderazgo" para atenuar las penalizaciones.
4. **Incertidumbre:** Se "tira un dado virtual". Si sale par, se extrae y aplica una carta de "Realidad Organizacional" (evento aleatorio). Si sale impar, el entorno se mantiene estable.
5. **Resolución:** Se actualizan los KPIs. Si algún indicador llega a 0, se activa el protocolo de "Colapso Organizacional" (Game Over). De lo contrario, se avanza al siguiente mes.
6. **Eventos Especiales:** En los meses 5 y 12 de cada año, se interrumpen los dilemas normales para gestionar eventos financieros obligatorios (PTU y Aguinaldo).

---

## 🎯 ¿Para qué sirve? (Casos de Uso)
1. **Capacitación y Onboarding:** Herramienta didáctica para entrenar a nuevos mandos medios en la evaluación de *trade-offs* (compensaciones) entre finanzas, recursos humanos y operaciones.
2. **Portafolio de Desarrollo Frontend:** Demuestra dominio de manipulación del DOM, gestión de estado en JavaScript, diseño responsivo con CSS Grid/Flexbox y lógica de algoritmos (barajado, validación de condiciones).
3. **Prototipado de Mecánicas:** Sirve como base o *boilerplate* para desarrolladores que deseen construir juegos serios (*serious games*) o simuladores de negocios más complejos.
4. **Evaluación de Pensamiento Sistémico:** Permite a los usuarios experimentar cómo una decisión aparentemente beneficiosa a corto plazo (ej. recortar presupuesto) puede desencadenar fallos en cadena a largo plazo.

---

## 🛠️ Tecnologías Utilizadas
* **HTML5:** Estructura semántica y modales nativos.
* **CSS3:** Variables CSS (Custom Properties) para theming, Flexbox y CSS Grid para el diseño responsivo, y animaciones CSS para las transiciones y el efecto del dado.
* **JavaScript (ES6+):** 
  - Manipulación del DOM sin librerías.
  - Algoritmo de barajado *Fisher-Yates* para garantizar aleatoriedad sin repetición.
  - Gestión de estado mediante un objeto central `state`.
  - Funciones flecha, desestructuración y métodos de array (`map`, `forEach`, `filter`).

---

## 🚀 Cómo Ejecutar el Proyecto

Dado que es una aplicación estática, no requiere instalación de dependencias (`npm install`) ni compilación.

### Opción 1: Ejecución Directa (Recomendada para pruebas rápidas)
1. Descarga o clona el repositorio.
2. Abre el archivo `index.html` directamente con cualquier navegador web moderno (Chrome, Firefox, Edge, Safari).

### Opción 2: Servidor Local (Recomendada para desarrollo)
Si utilizas VS Code, instala la extensión **Live Server**, haz clic derecho en `index.html` y selecciona "Open with Live Server". Esto evitará cualquier restricción de CORS si en el futuro decides cargar datos externos.

---

## 📂 Estructura del Código
El proyecto está contenido en un único archivo `index.html` para facilitar su portabilidad y despliegue inmediato (por ejemplo, en GitHub Pages o Netlify Drop). Internamente, el código está organizado en secciones claras:
1. **`<style>`:** Variables de diseño, layout responsivo y estilos de componentes (tarjetas, modales, barras de progreso).
2. **`const DILEMAS` / `const CONSECUENCIAS`:** Bases de datos en formato JSON/Array que contienen la narrativa y los valores numéricos de impacto.
3. **`let state`:** Objeto central que almacena el mes actual, los valores de los KPIs, el mazo de cartas y el historial.
4. **Funciones de Lógica:** `drawDilema()`, `applyEffects()`, `rollEnvironmentDice()`, `checkStreak()`, etc.
5. **Funciones de Renderizado:** `renderDashboard()`, `renderLog()`, que actualizan la interfaz de usuario en respuesta a los cambios de estado.

---

## 📄 Licencia
Este proyecto está disponible bajo la licencia MIT. Siéntete libre de usarlo, modificarlo y distribuirlo para fines educativos o comerciales.

---

### 💡 Sugerencia para tu repositorio:
1. Crea un nuevo repositorio en GitHub.
2. Sube el archivo `index.html` con todo el código que hemos desarrollado.
3. Crea un archivo llamado `README.md` y pega exactamente el texto de arriba.
4. Activa **GitHub Pages** en la configuración del repositorio (Settings > Pages > Source: main branch) para que tu simulador tenga una URL pública y funcional en minutos (ej: `tu-usuario.github.io/simulador-gerencial`).
