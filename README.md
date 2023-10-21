# Mecatrónica, modelado y control del robot aéreo de ala batiente HOMPOT (HOMing Pigeon bOT)
Proyecto Fin de Grado en Ingeniería Electrónica, Robótica y Mecatrónica

<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/hompot.png" width="800" />

- Este trabajo forma parte del desarrollo del proyecto HOMPOT de la Junta de Andalucía, dentro del marco PAIDI 2020, con financiación europea de fondos FEDER.

- El objetivo del breve resumen que se ofrece es dar conocimiento de los aspectos más relevantes tratados durante meses, a modo de muestra de la capacidad de trabajo personal.

- Debido a la confidencialidad del proyecto me limito a aportar únicamente resultados visuales conceptuales, sin desvelar detalles sensibles del trabajo desarrollado.

# PROPÓSITO DEL PROYECTO

El propósito que se persigue es el de crear un sistema robótico capaz de cumplir las funciones básicas de vuelo de un ornitóptero, del cual tengamos total control y conocimiento, que sirva de base para el desarrollo de tareas
autónomas.

Partiendo de la estructura aerodinámica previamente fabricada de un prototipo radiocontrol, se desea conseguir modificar el sistema mecatrónico y electrónico interno para que sea reprogramable. En este sentido, el aprovechamiento de los componentes y el estudio de diversas líneas de trabajo tanto como su ejecución práctica que sirvan como solución son esenciales.

El objetivo prioritario es la implementación de la parte hardware y software para volarlo con un control manual y automático propio, estableciendo un sistema de comunicaciones inalámbrico que permita el envío de comandos de control y la recepción de telemetría del vuelo. Esto último será muy importante para permitir un continuo avance en el proyecto.

Deberemos hacer frente a una serie de retos importantes asociados a este tipo de plataformas. El modelado aerodinámico es complejo al ser altamente no estacionario y no lineal. La capacidad de carga es reducida debido a la limitación de la propulsión. Restricciones de peso: el sistema con todos los cambios no debe ser excesivamente pesado puesto que lastraría el rendimiento de vuelo de la estructura usada como chasis. La tendencia irá encaminada a lograr un vuelo limpio y una maniobra de aterrizaje suave.

# MODELADO Y CONTROL

El modelado y simulación de nuestro ornitóptero serán unas herramientas esenciales para comprender y predecir el comportamiento aproximado de vuelo en la práctica. Nos permitirá realizar pruebas virtuales exhaustivas, optimizar el diseño, evaluando diferentes técnicas de control y simulando condiciones extremas. Su principal uso será el de conocer cuáles serán los trimados de vuelo entorno a los que desarrollar los controladores y pruebas de vuelo. Al aprovechar estas técnicas, se puede reducir el tiempo y los recursos necesarios para el desarrollo de nuestro proyecto mecatrónico, mejorando su rendimiento y aumentando la confianza en su comportamiento antes de su despliegue en el mundo real.

La herramienta elegida para hacer nuestros simuladores de vuelo ha sido SIMULINK y MATLAB.

<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/modelado.png" width="800" />
<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/graficas.png" width="800" />
<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/animacion.png" width="800" />

# AUTOPILOTO REMOTO POR RADIOFRECUENCIA

La implementación del control remoto en nuestro robot aéreo es una primera opción a tener en cuenta al presentar una notoria gama de ventajas. La más inmediata es atendiendo al peso del pájaro robótico. Al trasladar parte del procesamiento y cálculo a un sistema centralizado en tierra, el robot no necesitaría de nueva electrónica extra que influya en el vuelo, debido al incremento de peso. A su vez, permitiría aumentar la capacidad de carga útil, aprovechándola para transporte de algún objeto involucrado en alguna tarea avanzada que pueda desarrollarse. 

Otras virtudes de esta filosofía de trabajo serían un menor coste computacional a bordo y por tanto una menor complejidad, evitando la inclusión de nuevo hardware. Siguiendo en esta idea, también estaría asociado en consecuencia una disminución del consumo, lo cual se traduce en una mayor duración de la batería. Además, el hecho de tener una estación de procesamiento en tierra permite usar recursos que en aire no son posibles debido a tamaño y peso.

En este sentido, el aprovechamiento y desarrollo sobre la comunicación a través de radiofrecuencia establecida
de fábrica puede ser una buena línea de trabajo.

En este apartado se propone el control actuando sobre el mando radiocontrol original, el cual será convenientemente adaptado, para transmitir por radiofrecuencia las órdenes necesarias para controlar al ornitóptero, tal y como lo haría un piloto. Para ello será necesario el uso de un microcontrolador en tierra que contenga el autopiloto donde se ejecute el programa encargado de generar las señales de control, además de cierta electrónica intermedia. Esto permitirá el aprovechamiento de todos los componentes de a bordo y del funcionamiento interno del producto.

<div style="display: flex; flex-direction: row;">
  <img src="https://github.com/aglora/HOMPOT/blob/main/imgs/MONTAJE_mejora1.jpg" width="220" />
  <img src="https://github.com/aglora/HOMPOT/blob/main/imgs/MONTAJE_mejora2.jpg" width="220" />
  <img src="https://github.com/aglora/HOMPOT/blob/main/imgs/MONTAJE_mejora3.jpg" width="360" />
</div>
<img src="https://github.com/aglora/HOMPOT/blob/main/gifs/auto_rf.gif" width="800" />

Debido a las condiciones externas y vuelo realista las trayectorias seguidas han variado respecto de la ideal en un plano vertical esperada. En esto influye multitud de factores como: el lanzamiento inicial, la fuerza y
dirección del viento existente, el desequilibrio en alas por asimetrías de fabricación y ajustes no del todo buenos. Sin embargo, en varios experimentos se han conseguido resultados bastante aceptables teniendo en
cuenta que estamos en bucle abierto y no rechazamos todas esas perturbaciones comentadas.

<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/vuelo_Autopiloto_RF.png" width="800" />

Esta línea de trabajo existe un claro inconveniente: no hay disponemos de realimentación, lo que dificultaría el desarrollo de cualquier tarea autónoma que la requiera.
Decidimos optar por un montaje propio del sistema, aprovechando al máximo los recursos disponibles, que permita cerrar el bucle directamente en el propio ornitóptero.

# DISEÑO, PRUEBAS Y MONTAJE HARDWARE

Implementamos un nuevo sistema electrónico personalizado a bordo del robot, incorporando nuevos sensores y aprovechando actuadores tras una profunda caracterización e ingeniería inversa. Esta estrategia nos permitirá reprogramarlo según nuestras preferencias y necesidades, para desarrollar y depurar diversos programas con funcionalidades distintas. 

Diseño y la creación de un prototipo funcional, que posteriormente nos brindará la capacidad de establecer modos de funcionamiento tanto manuales como automáticos.

<img src="https://github.com/aglora/HOMPOT/blob/main/gifs/montaje.gif" width="800" />

Componentes usados para la integración del sistema:

- **Sensor de efecto Hall**: Medida de la frecuencia de aleteo
- **Sensor barómetro BMP280**: Estimación de la altura
- **IMU MPU6050**: Estimación de la orientación
- **Servomotores**: Flaps de cola
- **Placa ESC y motor BLDC**: Movimiento del mecanismo de las alas
- **Placa WeMos D1 Mini Wi-Fi con microcontrolador ESP8266**: Placa principal con microcontrolador de a bordo
- **Batería ion-Litio 2S 520mAh**: Alimentación del ornitóptero

<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/montaje.png" width="800" />


# AGRADECIMIENTOS

José Ángel Acosta Rodríguez

Cristina Ruiz Páez
