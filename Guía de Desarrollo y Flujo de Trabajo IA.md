# Guía Definitiva: Godot, Antigravity, Prompting Estructurado y Diseño Asistido por IA

Esta guía documenta las mejores prácticas para el desarrollo de videojuegos utilizando Godot Engine (con mecánicas de antigravedad/gravedad direccional), la creación de *prompts* estructurados (evitando el *vibe coding*), y el uso de herramientas de diseño optimizadas para la colaboración con Inteligencia Artificial.

---

## 1. Godot y "Antigravity": Mejores Prácticas de Desarrollo

Trabajar con mecánicas de antigravedad o gravedad dinámica (como caminar por paredes o planetas esféricos) en Godot requiere un manejo preciso de las físicas.

### Arquitectura y Nodos
*   **Uso de `CharacterBody3D` (Godot 4.x):** Es el nodo ideal. Permite modificar la propiedad `up_direction` dinámicamente. Esto es crucial para que funciones integradas como `is_on_floor()` sigan funcionando correctamente sin importar la orientación del personaje.
*   **Zonas de Gravedad con `Area3D`:** Utiliza nodos `Area3D` con la propiedad `gravity_space_override` activada. Godot permite que estas áreas alteren la dirección de la gravedad de los cuerpos físicos que entran en ellas (Point gravity para planetas, Directional para paredes).
*   **Separación de Lógica (Componentes):** No pongas todo el código en el jugador. Crea un `GravityController` (Node) que calcule el vector de gravedad hacia la superficie más cercana usando `RayCast3D` y alimente ese vector al script de movimiento principal.

### Manejo de Físicas
*   **Quaternions (Cuaterniones):** Para rotar al personaje hacia la nueva gravedad suavemente sin sufrir el *Gimbal Lock*, utiliza `Quaternion` o la función `Basis.looking_at()`. Evita manipular los ángulos de Euler (`rotation.x`, `rotation.y`) directamente.
*   **Alineación de Mallas:** Mantén la malla visual (`MeshInstance3D`) separada del colisionador. Rota visualmente el modelo hacia la gravedad utilizando interpolación (`lerp` o `slerp`) en la función `_process`, mientras las físicas puras se calculan en `_physics_process`.

---

## 2. Ingeniería de Prompts: Cero "Vibe Coding"

El *vibe coding* consiste en dar instrucciones vagas a la IA y esperar que adivine la intención (ej. "Haz que el jugador se mueva chido"). Para entornos profesionales, se requiere **Prompting Determinista**.

### Estructura de un Prompt Eficiente
Para obtener código funcional y predecible a la primera, usa un formato estructurado (como el marco **C.R.E.A.T.E.**):

1.  **Contexto (Context):** Define el entorno técnico exacto.
    *   *Ejemplo:* "Estás actuando como un Senior Gameplay Programmer en Godot 4.3 usando GDScript."
2.  **Requisito (Request):** La tarea específica.
    *   *Ejemplo:* "Escribe un script para CharacterBody3D que alinee el `up_direction` a la normal de la superficie."
3.  **Explicación (Explanation):** La lógica matemática o de negocio.
    *   *Ejemplo:* "Usa un RayCast3D apuntando hacia -Y (local). Interpola la rotación usando Quaternions con un peso de 10 * delta."
4.  **Acción (Action):** Qué debe hacer exactamente la IA.
    *   *Ejemplo:* "Proporciona solo el bloque de código de GDScript. No expliques qué es un Quaternion."
5.  **Restricciones (Constraints):** Edge cases.
    *   *Ejemplo:* "No uses `move_and_collide`, usa `move_and_slide`. Asegúrate de que la cámara no gire bruscamente."

---

## 3. Entrega y Administración de Prompts

Para no malgastar *tokens* (reduciendo costos y mejorando la atención del modelo), la forma en que entregas la información es vital:

*   **Prompting Progresivo (Chain of Thought):** No pidas un sistema completo en un solo mensaje. Primero pide la estructura de clases, luego la lógica de físicas, y por último la interpolación visual.
*   **Inyección de Contexto Estático:** Crea un archivo `rules.md` o `architecture.txt` en tu repositorio. Antes de empezar a programar, envía este archivo a la IA. Debe contener tus convenciones de nombres, estructura de carpetas y versiones de software.
*   **Uso de "Few-Shot Prompting":** Pásale a la IA 1 o 2 ejemplos de código tuyo que ya funcione para que imite exactamente tu estilo de formateo, espaciado y comentarios.
*   **Herramientas de IDE:** En lugar de copiar y pegar en un navegador, usa herramientas integradas como *GitHub Copilot*, *Cursor* o *Cline*, donde la IA puede leer el árbol de directorios directamente, ahorrando tokens de descripción.

---

## 4. Herramientas de Diseño Compatibles y "AI-Friendly"

Para que la IA pueda ayudarte a diseñar texturas, modelado y mallas sin consumir millones de tokens en imágenes inútiles, debes usar herramientas que basen sus archivos en **código, nodos o texto plano (JSON/Python)**.

### Modelado 3D y Mallas
*   **Blender (La mejor opción absoluta):**
    *   *Por qué es eficiente:* Blender tiene una API de Python extremadamente robusta (`bpy`). En lugar de pedirle a la IA que "genere un modelo 3D", **pídele que genere un script de Python para Blender**. La IA te dará 50 líneas de código (muy pocos tokens) que, al ejecutarse en Blender, generarán mallas procedimentales, estructuras o herramientas de automatización perfectas.
*   **Blockbench:**
    *   *Por qué es eficiente:* Muy popular para estilos low-poly. Guarda los modelos en formato JSON, el cual la IA puede leer, analizar y modificar estructuradamente si necesitas que ajuste coordenadas de mallas simples.

### Texturas y Materiales
*   **Material Maker (Ecosistema Godot):**
    *   *Por qué es eficiente:* Es un creador de materiales PBR procedurales basado en nodos (similar a Substance Designer) pero open source. Sus proyectos se guardan en JSON. Puedes describir un material a la IA y pedirle que te genere la estructura de nodos en JSON, optimizando el ancho de banda.
*   **Krita (con Krita AI Diffusion plugin):**
    *   *Por qué es eficiente:* En lugar de usar Midjourney, puedes usar Krita con este plugin local (ComfyUI/Stable Diffusion). Mantienes un control absoluto sobre capas y máscaras. Para la comunicación de texto con LLMs (como Gemini), puedes pedir descripciones exactas de paletas de colores en HEX o matrices de convolución para filtros.

### Resumen de Eficiencia de Tokens en Diseño:
La regla de oro es: **La IA no debe escupir píxeles ni vértices directamente; la IA debe escupir el código procedimental o la fórmula matemática que genera esos píxeles o vértices.**

---
*Documento generado para estandarización de flujos de trabajo en desarrollo de videojuegos con IA.*