SIMULACIONES A ANALIZAR:

✅ 1. Revisa detalladamente el ejemplo 4.2: an [Array of Particles](https://natureofcode.com/particles/#example-42-an-array-of-particles).

**Código original**

[Aquí](https://editor.p5js.org/WatermelonSuggar/sketches/rX71fPRay)

> ¿Cómo se está gestionando la creación y la desaparción de las partículas y cómo se gestiona la memoria en cada una de las simulaciones?

* **Asignación de memoria**

1. Cada vez que creamos una Particle, se reserva espacio en la memoria para su posición, velocidad, aceleración y otros atributos.
2. Si no elimináramos partículas, el array particles crecería infinitamente, causando problemas de rendimiento.

* **Liberación de memoria**
1. Cuando una partícula muere, se elimina del array con splice (i, 1), lo que hace que JavaScript libere su referencia en memoria y permita que el garbage collector la elimine en algún momento. Este enfoque es eficiente porque JavaScript maneja la memoria automáticamente, pero si el número de partículas fuera muy alto, podríamos optimizarlo más.

**Código modificado**

[Aquí](https://editor.p5js.org/WatermelonSuggar/sketches/xASgHG0km)

> 🌳Vas a gestionar la creación y la desaparición de las partículas y la memoria. Explica cómo lo hiciste.

* Hice que las partículas aparezcan y desaparezcan de manera controlada. Con este sistema, evitamos que el programa se vuelva lento por tener demasiadas partículas al mismo tiempo.

* Creación:
  * Cada vez que el programa dibuja un nuevo cuadro, revisa qué tan rápido se está moviendo el mouse.
  * Si el mouse está quieto, aparecen pocas partículas.
  * Si el mouse se mueve rápido, aparecen más.
  * Las partículas se crean justo en la posición del mouse y empiezan a moverse solas.

* Desaparición:
  * Cada partícula tiene un "tiempo de vida" que se va reduciendo con el tiempo.
  * Cuando su tiempo de vida llega a 0, la eliminamos del arreglo que las guarda.
  * Si ya hay muchas partículas, también eliminamos algunas para que la pantalla no se llene demasiado.

> 🌳Explica qué concepto aplicaste, cómo lo aplicaste y por qué.

**Concepto aplicado**
*  Apliqué una **fuerza de atracción inversamente proporcional a la distancia**, es decir que, si la partícula está lejos del mouse, la atracción es más débil. Si la partícula está cerca del mouse, la atracción es más fuerte.

**Cómo lo apliqué**

* Calculé la dirección hacia el mouse, para cada partícula, obtuve un vector que apunta desde su posición hasta el mouse.
* Medí la distancia entre la partícula y el mouse, esto me permite ajustar la intensidad de la atracción.
* Normalicé el vector para que solo indique dirección, así evité que partículas muy lejos reciban una fuerza excesiva.
* Multipliqué la fuerza por un valor inversamente proporcional a la distancia
* Apliqué la fuerza a la partícula, lo que hace que la partícula cambie su aceleración y se mueva hacia el mouse.


**¿Por qué?**

*  Para que las partículas reaccionen al mouse de forma natural en lugar de moverse de manera brusca.
*  Si usara una fuerza constante, todas las partículas se moverían igual sin importar la distancia y haría que la simulación fuera monótona.
*  Para mejorar la visualización de la simulación, dándole una mejor interacción y dinamismo con el mouse.

_______________________________________________________________________________________________________________________________________________

✅ 2. Analiza el ejemplo 4.4: a System of Systems.

✅ 3. Analiza el ejemplo 4.5: a Particle System with Inheritance and Polymorphism.

✅ 4. Analiza el ejemplo 4.6: a Particle System with Forces.

✅ 5. Analiza el ejemplo 4.7: a Particle System with a Repeller.

PARA CADA UNA DE LAS SIMULACIONES:


> Vas a gestionar la creación y la desaparición de las partículas y la memoria. Explica cómo lo hiciste.

📤 Entrega:

1. Vas a modificar cada una de las simulaciones anteriores incluyen en cada una, al menos un concepto de las unidades anteriores, pero no repitas concepto, la idea es que repases al menos uno de cada unidad.
2. Vas a gestionar la creación y la desaparición de las partículas y la memoria. Explica cómo lo hiciste.
3. Explica qué concepto aplicaste, cómo lo aplicaste y por qué.
4. Incluye un enlace a tu código en el editor de p5.js.
5. Incluye el código fuente de cada una de las simulaciones.
6. Captura de pantallas de cada una de las simulaciones con las imágenes que más te gusten como resultado de la ejecución de cada una de las simulaciones.
