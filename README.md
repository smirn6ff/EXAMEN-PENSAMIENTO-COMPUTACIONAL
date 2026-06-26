# EXAMEN-PENSAMIENTO-COMPUTACIONAL
Examen / Pensamiento Computacional

# Generador Interactivo de Paletas de Colores (p5.js)

![Pantalla Principal](pantalla%201.png)

## Enlaces del Proyecto
* **Link publico :** https://editor.p5js.org/sai666/full/sT7YNdtXE
* **Link editable:** https://editor.p5js.org/sai666/sketches/sT7YNdtXE

---

## Informacion del Proyecto
* **Nombre del proyecto:** Generador de Paleta de Colores
* **Autor:** Sai Jordán Lazo
* **Ramo:** Pensamiento Computacional / UDP

---

## Descripcion General

### Descripcion objetiva
* **Que es el proyecto:** Es una aplicacion web interactiva desarrollada en p5.js que funciona como una herramienta de asistencia de diseño para la creacion, visualizacion y exportacion de paletas cromaticas de 4 elementos en formato RGB.
* **Que se ve en pantalla:** Una interfaz oscura y minimalista con un video abstracto en bucle de fondo. Dependiendo del estado, se visualizan diferentes botones interactivos, formas con 4 muestras cuadradas de color, sliders y botones de accion.
* **Que elementos visuales aparecen:** Cuatro lienzos cuadrados, tres sliders para los canales Rojo (R), Verde (G) y Azul (B), titulos, botones de navegacion y una capa de transicion tipo fade in/fade out cadda vez que el estado cambia.
* **Que inputs utiliza:** Coordenadas espaciales del cursor (mouseX, mouseY), eventos de clic (mousePressed) y valores numericos tomados de los sliders.
* **Que outputs genera:** Renderizado de graficos vectoriales (paleta de color) 2D en tiempo real, salida de audio, reproduccion de video en bucle y descargas directas de imagenes en formato JPG.

### Descripcion conceptual
* **Idea central:** Facilitar la creacion de paletas cromáticas mediante una herramienta digital intuitiva y funcional. El proyecto se centra en optimizar la experiencia del usuario (UX) proponiendo dos flujos de trabajo directos; un control manual preciso mediante deslizadores y una generacion rapida a traves de funciones aleatorias.
* **Corriente o referente de diseno:** Diseno de Interfaces de Usuario (Ui/UX). La interfaz usa como referencia la convencion moderna del Modo Oscuro para minimizar las distracciones, reducir la fatiga visual y maximizar el contraste de los colores generados en los lienzos.
* **Referentes visuales, historicos o teoricos:** Se apoya en las heuristicas de usabilidad de Jakob Nielsen, especificamente en la visibilidad del estado del sistema (entregando feedback visual y sonoro inmediato ante cada accion) y en el control y libertad del usuario (ofreciendo opciones claras de navegacion y retorno entre pantallas).
* **Principio de diseno explorado:** Jerarquia visual (guiar el ojo hacia las funciones principales), consistencia y feedback inmediato (la respuesta instantanea que da el programa cuando haces clic en algo).

---

### Sistema Computacional

* **Inputs:** El sistema recibe datos a traves de las coordenadas espaciales del cursor (mouseX, mouseY), eventos de clic del usuario (mousePressed) y valores numericos continuos (del 0 al 255) obtenidos mediante el arrastre de los tres deslizadores (sliders).
* **Procesos:** El programa utiliza un bucle (for) para dibujar gradientes, la funcion matematica map() para calcular la opacidad de las transiciones, condicionales (if/else if) para enrutar los datos de color a la figura correcta, y algoritmos de generacion de numeros aleatorios (random) para crear combinaciones cromaticas.
* **Estados:** El programa se rige por la variable global "escena", la cual define tres estados principales: 0 (Pantalla de inicio), 1 (Generador manual) y 2 (Generador aleatorio). Ademas, cuenta con un estado secundario definido por la variable "figuraSeleccionada" (1, 2, 3 o 4) que indica cual de los cuatro cuadrados esta activo para edicion.
* **Eventos:** El ciclo de vida del sistema se basa en: preload() para la carga anticipada de archivos, setup() para la inicializacion del entorno, draw() que ejecuta el renderizado visual a 60 cuadros por segundo, y mousePressed() que captura las acciones fisicas del usuario.
* **Outputs:** Como salida, el sistema genera renderizado grafico 2D en pantalla, emision de sonido, reproduccion de video digital y la compilacion y descarga de archivos de imagen en formato JPG en el dispositivo del usuario.

---

### Explicacion de la Interaccion

* **Que datos entran al sistema:** Entran coordenadas numericas exactas cada vez que el usuario hace clic en la pantalla, ademas de los valores del nivel de Rojo, Verde y Azul definidos por la posicion fisica de los sliders.
* **Como se procesan:** El sistema procesa los clics verificando matematicamente si las coordenadas del raton coinciden con las areas invisibles (hitboxes) definidas sobre los botones y los cuadrados. Si hay coincidencia, el codigo aprueba la accion.
* **Como se transforman:** Los valores de los sliders se transforman directamente en variables de relleno de color (fill) asignadas a la figura activa. Por otro lado, los clics en los botones transforman el flujo del programa, alterando el numero de la variable "escena" o asignando valores completamente nuevos a los colores mediante la funcion random().
* **Que respuestas producen:** El sistema produce respuestas visuales inmediatas (actualizacion del color en tiempo real y transiciones de pantalla con fade a negro), respuestas auditivas (sonidos de confirmacion de clic) y respuestas de hardware (ordenar al navegador web que descargue la paleta creada como una imagen JPG).

---

### Recursos Multimedia Utilizados

| Tipo de recurso | Nombre del archivo | Funcion que cumple dentro del proyecto |
| :--- | :--- | :--- |
| **Video** | fondo.mp4 | Se reproduce en bucle continuo con opacidad reducida para aportar textura visual a la interfaz. |
| **Audio** | sonido1.mp3 | Proporciona feedback auditivo para confirmar interacciones comunes, como avanzar de pantalla, seleccionar un color o guardar la paleta. |
| **Audio** | sonido2.mp3 | Proporciona un feedback auditivo distinto para enfatizar acciones disruptivas o de cambio, especificamente al interactuar con el boton Random. |

---

## Registro Visual

### Referentes
* Se contemplaron interfaces de usuario modernas en Modo Oscuro de aplicaciones de diseno actuales. Se busco imitar la sobriedad, los contrastes altos y la limpieza en la distribucion de figuras y botones.


### Bocetos
* El diseno inicial de la interfaz se estructuro mediante wireframes basicos para definir la distribucion de los elementos. Se decidio colocar la matriz de muestras en la parte superior y agrupar los controles interactivos en la zona inferior y lateral derecha para un flujo de lectura natural.
* imagen]
---

## Reflexion Final

* **Principales decisiones tomadas:** La decision mas importante fue limitar el espacio de color a los canales RGB solidos, eliminando la transparencia. Esto aseguro la nitidez de los colores exportados y mejoro la relacion de contraste frente al fondo en movimiento. Ademas, priorizar la inclusion de texto explicitas y un boton de navegacion de retorno transformo el sketch de un experimento visual pasivo a una herramienta de software usable y clara.
* **Dificultades encontradas:** El principal obstaculo tecnico fue lidiar con el comportamiento de los sliders nativos de p5.js, los cuales no respetaban los limites del lienzo grafico y persistian visibles en pantallas donde no correspondia. Se soluciono aislando su comportamiento mediante show() y hide() vinculadas exclusivamente a los cambios del estado de la escena.
* **Aprendizajes obtenidos:** El desarrollo de este proyecto demostro que la programacion interactiva requiere una planificacion rigurosa de la experiencia de usuario (UX). Aprendi que inyectar confirmaciones visuales inmediatas (como transiciones fluidas de opacidad) y auditivas transforma la percepcion del usuario, haciendo que el sistema se sienta reactivo, profesional y confiable.

---


### Diagrama de flujo
