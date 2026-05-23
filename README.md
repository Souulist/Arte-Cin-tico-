# ARTE CINÉTICO — Sketch p5.js

- Autor
Florencia Iturrieta Garroz

- Descripción del proyecto

Este proyecto consiste en un sketch interactivo desarrollado en p5.js inspirado en el arte cinético y la visualización generativa.

El sistema produce composiciones visuales en blanco y negro mediante movimiento continuo, variaciones geométricas y respuestas en tiempo real a los inputs del usuario.

La propuesta explora la relación entre:
- movimiento
- repetición
- interactividad
- transformación visual

- ¿Qué se ve en pantalla?

El sketch genera una composición cinética compuesta por:
- líneas
- círculos
- puntos dinámicos
- movimiento continuo

Las formas reaccionan al:
- movimiento del mouse
- clicks
- teclado

El resultado visual cambia constantemente según las acciones del usuario.

- Descripción conceptual

La propuesta toma referencias del:
- arte cinético
- sistemas generativos
- visualización algorítmica
- composición minimalista en blanco y negro

El proyecto busca explorar cómo reglas simples pueden generar resultados visuales dinámicos y cambiantes mediante programación interactiva.


- Referentes

- Arte cinético
- Bridget Riley
- Julio Le Parc

- Arte generativo
- Casey Reas
- Processing / p5.js

- Referente visual
- Estética minimalista inspirada en interfaces tipo Cosmos

- Sistema de Input / Output

- Inputs

- Mouse
- Movimiento horizontal y vertical
- Click sostenido

- Teclado
- Barra espaciadora:
  cambia el modo visual

- Tecla "R":
  genera valores aleatorios

- Procesos

El sistema utiliza:
- variables,
- condicionales,
- loops,
- map(),
- random(),
- y funciones propias.

La posición del mouse modifica:
- tamaño,
- composición,
- y comportamiento visual.

Las decisiones lógicas permiten cambiar entre distintos estados gráficos.

- Outputs

El sketch genera:
- líneas dinámicas,
- círculos cinéticos,
- puntos reactivos,
- y animaciones generativas.

Todo el output visual ocurre en tiempo real.

- Diagrama de flujo
![Diagrama de flujo](./Diagrama%20de%20Flujo(1).png)

- Imágenes del proyecto
- ## Proceso
![Proceso 1](./Captura%20de%20pantalla%20(54).png)
![Proceso 1](./Captura%20de%20pantalla%20(55).png)
![Proceso 1](./Captura%20de%20pantalla%20(57).png)
![Proceso 1](./Captura%20de%20pantalla%20(58).png)
![Proceso 1](./Captura%20de%20pantalla%20(60).png)
![Proceso 1](./Captura%20de%20pantalla%20(61).png)
![Proceso 1](./Captura%20de%20pantalla%20(62).png)
![Proceso 1](./Captura%20de%20pantalla%20(64).png)
![Proceso 1](./Captura%20de%20pantalla%20(65).png)
![Proceso 1](./Captura%20de%20pantalla%20(66).png)
![Proceso 1](./Captura%20de%20pantalla%20(67).png)

- Captura del sketch
  ![Resultado](./Captura%20de%20pantalla%20(72).png)
  ![Resultado](./Captura%20de%20pantalla%20(74).png)
- Link P5JS
  [https://editor.p5js.org/220964701/sketches/YqWMrvw0c]
  
-CÓDIGO 
function setup() {
  createCanvas(800, 800);

  // Fondo blanco inicial
  background(255);
}

// Variable para cantidad de figuras
let cantidad = 40;

// Variable para velocidad del movimiento
let velocidad = 2;

// Variable para cambiar entre modos visuales
let modo = 0;



function draw() {

  // OUTPUT VISUAL DINÁMICO Y REACTIVO      

  // Fondo con transparencia para dejar rastros
  background(255, 20);


 
  // INPUT CONTINUO 
  // mientras el mouse se mueve


  // FUNCIÓN map() 

  let tamaño = map(mouseX, 0, width, 5, 80);

  // BUCLE 
  // Genera figuras 

  for (let i = 0; i < cantidad; i++) {

    // Posiciones variables
    let x = width / 2 + sin(frameCount * 0.01 + i) * 200;
    let y = height / 2 + cos(frameCount * 0.01 + i) * 200;
  
    // CONDICIONAL if 
   // Cambia el dibujo dependiendo del modo

    if (modo == 0) {

      // Líneas cinéticas
      stroke(0);

      line(x, y, mouseX, mouseY);

    } else {

      // Círculos cinéticos
      noFill();
      stroke(0);

      ellipse(x, y, tamaño, tamaño);

    }

  // CONDICIONAL if 

    if (mouseIsPressed) {

      fill(0);
      noStroke();

      ellipse(x, y, 10, 10);

    }

  }

}
// FUNCIÓN PROPIA 

function keyPressed() {

  // Tecla ESPACIO cambia el modo visual
  // VARIANTE GENERADA POR IF + TECLA

  if (key == ' ') {

    modo++;

    // Alterna entre 0 y 1
    if (modo > 1) {
      modo = 0;
    }

  }

  // Tecla R genera resultados diferentes aleatorios
  // VARIANTE GENERADA POR LOOP + RANDOM + TECLA

  if (key == 'r' || key == 'R') {

    cantidad = random(5, 100);

  }

}         

-- Tecnologías utilizadas
- p5.js
- JavaScript
- Canva
- GitHub
