
## Integrantes:

- Isidora Alvarez
- Dayana Pañitrur

## **Investigación**

**Open CV**
*Open Source Vision Library*

Biblioteca libre de código abierto especializada en visión por computadora
Procesa imágenes y videos en tiempo real
Cambia tamaños, recorta, filtra colores, ajusta brillos o convertir imágenes a escala de grises.

Lenguajes: Python, C++ y Java 

¿Cómo se ejecuta?: No es un software ejecutable con interfaz gráfica o botones (como Photoshop), sino una librería de herramientas que se controla escribiendo código. 

Editores de código: Visual Studio Code, PyCharm o Google Colab para redactar y ejecutar los programas. 

tipos de visuales: 
Cuadros de delimitación (bounding boxes), texto e indicadores dibujados en tiempo real sobre una cámara.
Segmentación y máscaras de color (aislar un fondo o identificar objetos por su tono).
Filtros visuales, mapa de puntos de rastreo, detección de bordes y superposición de elementos gráficos (efectos de realidad aumentada básicos).

---

**Media Pipe**

> no necesita instalar programas 
Multiplataforma
> Conjunto de herramientas de código abierto.

*Permite crear soluciones de visión artificial y aprendizaje automático

Puede identificar puntos clave en el cuerpo humano, la cara y las manos.
  > Reconocimiento facial:
     > Seguimiento de gesto 
        > Detección de objetos
           > Seguimiento del cuerpo humano
              > Face Landmarker: Detecta 468 puntos en el rostro (ideal para ubicar la posición exacta de ojos y labios).
                > Pose Landmarker: Detecta 33 puntos del cuerpo completo (ideal para ubicar hombros, codos y torso).
                   > Hand Landmarker: Detecta 21 puntos por cada mano (ideal para rastrear las puntas de los dedos).

**usa modelos de Inteligencia Artificial (Deep Learning: es ai basada en redes neuronales que les permite a las máquinas aprender y tomar decisiones a través de datos)**

---

**Three.js**

 - Biblioteca de JavaScript para renderizar en 3d.
            > Generar y animar gráficos en 3D dentro del navegador 
               >  Se puede manipular luces, cámaras, animar objetos, perspectivas, control de visualizaciones, etc.
**Solo usa archivos en formato .glb** 

## **Multirealidades**

**Multirealidades**

Es una pagina web de arte y tecnología con estética retro de sistemas operativos de los años 2000 (Y2K / Windows XP). El proyecto explora cómo la presencia y el movimiento del cuerpo humano pueden alterar, distorsionar o construir la realidad digital a través de la cámara web.

---

##  **Arquitectura del Sistema**

El sistema consta de:
- **una pantalla**
- **una cámara web** 
- **tres sistemas interactivos**
- Que operan de manera simultánea.


---


Para hacer estos 3  sistemas no instalamos ningún paquete ni dependencias pesadas en los computadores. Todo el proyecto funciona mediante tecnologías web estándar y librerías externas que se cargan directamente en tiempo de ejecución mediante CDN (Content Delivery Network) con etiquetas de script:
HTML5 y CSS3: Para estructurar el diseño clásico de ventanas flotantes con bordes biselados y tipografías retro.*

- OpenCV.js: Para el procesamiento de fotogramas y visión por computador del primer sistema.*
- MediaPipe: Para el reconocimiento de inteligencia artificial y seguimiento de manos mediante redes neuronales.*
- Three.js y GLTFLoader: Para el motor gráfico en 3D (WebGL) encargado de renderizar los modelos tridimensionales.


---


| Sistema 1: OpenCV (Detección de Movimiento y Quietud) | Sistema 2: MediaPipe (Detección de Manos y Gestos) | Sistema 3: Three.js (Integración y Realidad Tridimensional) |
| :--- | :--- | :--- |
| Mide la ausencia de movimiento, si el usuario se queda completamente quieto frente a la cámara, el sistema calcula la diferencia de luminancia entre fotogramas consecutivos e incrementa un nivel de distorsión y ondas cromáticas, simulando una 'alucinación' visual. Al moverse, la imagen vuelve a la normalidad al instante.<br><br>**Detección de Movimiento y Quietud:**<br>Este módulo analiza los fotogramas de vídeo fotograma a fotograma evaluando la dinámica del entorno.<br><br>**Control de Sucesos / Construcción de la Realidad:**<br>* **Objetivo:** Lograr que el movimiento y la quietud funcionen como detonantes de una realidad alterada fuera de nuestra percepción ordinaria.<br>* **Interacción:** Si hay movimiento en la escena, la pantalla mantiene su **nitidez**. A mayor quietud y permanencia del usuario, mayor será el efecto de distorsión/alucinación cromática y ondulatoria en el entorno visual. | Rastrea las manos del usuario mediante IA. Al realizar el gesto específico de “Cámara” con ambas manos y a medida que se van separando las manos se proyecta partículas brillantes interactivas sobre la silueta del cuerpo de la persona. Además, al pasar el cursor sobre la tarjeta de texto, el sistema despliega automáticamente una guía visual flotante con la postura correcta que se debe hacer para que se active.<br><br>**Puntos Exactos a Detectar (Landmarks):**<br>* **Articulaciones de los dedos (Puntas y nudillos):** El modelo detecta 21 puntos clave por cada mano para calcular distancias geométricas exactas.<br>* **Coordenadas del pulgar e índice:** Actúan como sensores de pinza para escalar y desplazar elementos.<br>* **Interacción bimanual:** Detecta la presencia simultánea de ambas manos para reconocer gestos complejos (como un marco).<br>> **¿Por qué estos puntos?:** Porque permiten una interacción gestual precisa y natural frente a la pantalla sin necesidad de periféricos físicos, utilizando las manos como herramientas directas de control.<br><br>**Control de Sucesos / Construcción de la Realidad:**<br>* **Condición de entrada:** La cámara detecta las manos del usuario frente al lente.<br>* **Interacción:**<br>  * Al hacer el gesto de **marco con dos manos**, se mide la apertura para controlar efectos visuales (como la opacidad de las partículas sobre el cuerpo).<br>  * Al juntar el **índice y el pulgar**, y cerrar los demás dedos en puño, se puede escalar y desplazar la figura tridimensional en tiempo real.<br>* **Palabras Clave:**<br>> Gesto<br>> Modificar<br>> Escala<br>> Espacio<br>El cuerpo controla y manipula los objetos virtuales según su posición anatómica. | Se Cargó un modelo tridimensional (.glb) hecho en Blender en el sistema. El usuario puede escalar el tamaño del objeto juntando y separando su dedo índice y pulgar. Al igual que se puede desplazar por la pantalla cerrando los demás dedos en un puño parcial.<br><br>**Integración y Realidad Tridimensional:**<br>Este canvas integra y combina los dos sistemas anteriores para crear una experiencia interactiva unificada.<br><br>**¿Cómo se logra la integración?:**<br>* **Control gestual MediaPipe:** Las posturas de los dedos, como la distancia entre índice y pulgar controlan el tamaño y la posición de los modelos 3D en tiempo real.<br>* **Filtro de entorno OpenCV/Video:** La cámara y las texturas actúan como fondos interactivos dentro del entorno WebGL (permite renderizar gráficos 2D y 3D directamente en navegadores web compatibles, sin necesidad de instalar complementos adicionales).<br>* **Modelos 3D (.glb):** Se integran modelos tridimensionales en formato estándar .glb, recopilando geometría, parámetros y materiales en un solo archivo optimizado.<br>El modelo 3D utilizado en la web se creó en Blender partiendo de una figura de una esfera o 'ball'. A partir de ahí, se duplicó, copió y pegó para ir modificando y esculpiendo las formas de acuerdo con el diseño deseado. Finalmente, toda la estructura geométrica se convirtió y fusionó en una malla/mesh, permitiendo exportar el objeto final en un único archivo en formato .glb listo para ser cargado y manipulado en tiempo real mediante Three.js en la página web.<br><br>![Render](imagen/render.png) |


---


## **Reflexión**

Cada individuo tiene una percepción de la realidad distinta a la de los demás, moldeada por sus experiencias físicas y emocionales, su contexto y su visión del mundo. Por más vivencias que compartamos con otras personas, nuestra percepción nunca es idéntica; construimos nuestro propio sistema para entender lo que nos rodea. Esto ocurre a través de nuestros sentidos el tacto, el oído, el gusto, el olfato y la vista, así como de la consciencia y la interpretación que hacemos de ellos.

Pero, ¿qué pasaría si estos sistemas de percepción no pertenecieran a un ser humano?

Multirealidades presenta tres sistemas que utilizan un mismo medio para recibir información: la cámara, pero la interpretan de tres maneras completamente distintas. Cada uno de estos sistemas es capaz de captar elementos que los demás omiten, entregando perspectivas y resultados únicos. Son datos que nosotros, por nuestra naturaleza, no lograríamos descifrar, pero que esta interfaz nos permite finalmente visualizar.

Estos tres sistemas actúan como una puerta a realidades que comúnmente omitimos, brindándole un medio para manifestarse a aquello que nuestros sentidos biológicos filtran.

"El cerebro puede actuar como una 'válvula reductora', filtrando la vastedad de la conciencia, lo que nos permite funcionar en la vida diaria".

— Huxley, A. (1954). Las puertas de la percepción.


---


## **Prompts**
Necesito desarrollar una interfaz web, la cual te explicaré el funcionamiento a lo largo de este prompt.

He trabajado muy poco en código antes, lo más mínimo. Por lo que hay muy pocas cosas que comprendo. Mi acercamiento a las páginas web también es vago por lo que necesito que me guíes en absolutamente cada paso a realizar para llevar a cabo este proyecto.

El proyecto trata de dos sistemas que por medio de una misma cámara pueden detectar o percibir cosas distintas, opencv detecta cosas de la realidad que normalmente no percibimos o no estamos conscientes y mediapipe a través del uso de las manos o de algún elemento corporal para controlar cosas en la pantalla.

Son 3 sistemas, son 3 pantallas/ventanas/recuadros en paralelo, presentadas en un solo frame.

Tecnologías requeridas:

-HTML5
-CSS
-JavaScript
-MediaPipe
-OpenCV
-Canvas2d

*Necesito que tengas en cuenta algo muy importante, no juntes los códigos de html. css y script, la idea es tenerlos por separado para trabajar de una manera ordenada.

## ARQUITECTURA Y LÓGICA DE LOS SISTEMAS

**Capa 1 (Fondo) - Sistema OpenCV:**
El Entorno y la Distorsión
 > Este sistema captura la cámara web en espejo y evalúa el movimiento general usando sustracción de fondo (frame differencing).
   > Si el usuario se mueve constantemente: El video de la cámara se renderiza nítido, limpio y normal. El movimiento "estabiliza" la realidad.
     > Si el usuario se queda quieto: Se inicia un contador de quietud. A medida que pasan los fotogramas sin movimiento, la imagen del video debe comenzar a distorsionarse progresivamente como una alucinación.
       > Efecto de Alucinación: ayúdame a trabajar alguna técnica para implementarlo de forma performante en JS (puede ser manipulando píxeles con distorsión de ondas senoidales, separación de canales RGB, glitch, o filtros dinámicos). Debe sentirse como si la realidad se derritiera o perdiera la cordura por la inactividad.

*En cuanto el sistema vuelve a detectar movimiento, el nivel de alucinación baja rápidamente hasta volver a la imagen limpia.*

**Capa 2 (Frente) - Sistema MediaPipe:**
El Cuerpo como Barrera
> Este sistema opera en un canvas y rastrea el cuerpo del usuario.
  > Identifica los landmarks de las manos (muñecas y puntas de los dedos índices).
    > La Acción: Dibuja figuras geométricas sólidas (cuadrados o círculos color negro puro) exactamente en las coordenadas de las manos.
      > El Rastro: Las figuras no se borran de inmediato de un frame a otro, sino que dejan una estela o rastro que se desvanece suavemente (usando destination-out con rgba(0,0,0,0.05) o similar).
        > Concepto: Al mover las manos y los brazos, el usuario "pinta" bloques negros en el aire para intentar tapar su rostro o la cámara. "El cuerpo construye una barrera espacial".

Por último, teniendo estos dos sistemas, quiero integrar un tercero:

Ya sea con las opciones anteriormente mencionadas. Cómo three.js o canvas2d

Necesito que no hagas todo sin explicar nada. necesito comprender a detalle para que sirve cada parte del código.

**Además mi editor de código será VSC.
No utilizaré Python.**

respuesta gemini Daya: https://share.gemini.google/iVsMM9xXYAE4

Respuesta gemini Isi: https://share.gemini.google/qzMD4GJ41iNU




