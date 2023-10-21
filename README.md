# Mecatrónica, modelado y control del robot aéreo de ala batiente HOMPOT (HOMing Pigeon bOT)
Proyecto Fin de Grado en Ingeniería Electrónica, Robótica y Mecatrónica

<img src="https://github.com/aglora/HOMPOT/blob/main/imgs/hompot.png" width="800" />

- Este trabajo forma parte del desarrollo del proyecto HOMPOT de la Junta de Andalucía, dentro del marco PAIDI 2020, con financiación europea de fondos FEDER.

- El objetivo del resumen que se ofrece es dar conocimiento del trabajo personal desarrollado durante meses.

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




<div style="display: flex; flex-direction: row;">

</div>

# AGRADECIMIENTOS
José Ángel Acosta Rodríguez
Cristina Ruiz Páez
