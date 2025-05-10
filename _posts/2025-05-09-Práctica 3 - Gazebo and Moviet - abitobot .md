---
title: Práctica 3 - Abitobot Pick and place in Gazebo and ROS2 
layout: post
post-image: "https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/MSR_img.jpg?raw=true"
description: Implemented my robot "Abitobot" in Gazebo and ROS2
tags:
- Práctica 3 - Abitobot implemented in Gazebo and ROS2
- Post
- Modelado y Simulación de Robots
- MSR
- python
- ROS2
- Gazebo
- Moveit 
- Pick and Place
---

En este post voy a explicar los datos obtenidos de la simulación e implementación de mi robot "Abitobot" en Gazebo usando ROS2 jazzy y Moveit realizando un pick and place:


Si alguna de las imagenes no funciona se pueden ver en el siguiente [enlace](https://github.com/vbarcena2020/abitobot/tree/main/images).
---

# **Gráficas Obtenidas** 

## Gasto parcial - Tiempo

<p align="center">
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/effort-time.png?raw=true" alt="effort-time.png">
</p>

En cuanto al gasto parcial frente al tiempo de los joints involucrados en la cinematica inversa se puede apreciar que:

- Al comienzo el gasto es minimo hasta los casi 40 segundos debido a que en ese periodo el robot solo se encuentra aproximandose al cubo por lo tanto el unico gasto que se aprecia es el esfuerzo por no moverse los joints durante el desplazamiento.

- Luego se aprecia un gran esfuerzo producido por el movimiento y levantamiento del cubo.

- Por ultimo se aprecia un mayor esfuerzo aun cuando el brazo baja el cubo para dejarlo. En cuanto lo deja el esfuerzo vuelve a ser casi minimo.

Todo este gran cambio en el esfuerzo del brazo se debe al peso añadido del cubo. Este porvoca que se deba hacer más fuerza para llegar a las poses requeridas.

## Posición ruedas Joint_States - Tiempo


<p align="center">
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/pose-time.png?raw=true" alt="pose-time.png">
</p>


Estas gráficas muestran la posición angular de las ruedas del robot frente al tiempo donde se puede apreciar que:

- Entre 0 y 20 segundos aproximadamente, todas las ruedas presentan un cambio significativo en su posición, siendo las ruedas izquierdas aumentan su posición y las ruedas derechas disminuyen su posición.

- Esto sugiere que se ha realizado un movimiento hacia adelante en línea recta, donde las ruedas del lado izquierdo giran en un sentido y las del derecho en el opuesto.

- A partir de 20 segundos aproximadamente, las curvas se estabilizan, indicando que el robot se detuvo y procedió a realizar la manipulación de los cubos.


## Aceleracion Imu - Tiempo

<p align="center">
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/acceleration-time.png?raw=true" alt="acceleration-time.png">
</p>

Esta gráfica representa la aceleración lineal en el eje X captada por la unidad de medición inercial (IMU) del robot a lo largo del tiempo donde se puede observar que:

- Hay grandes variaciones al principio de la manipulación de los 0 a 20 segundos, indicando que el robot estuvo acelerando, frenando o corrigiendo su trayectoria mientras realizaba el movimiento de las ruedas para aproximarse a los cubos.

- Luego, la aceleración se estabiliza cerca de cero, lo cual es coherente ya que el robot deja de desplazarse cuando llega a los cubos a los aproximados 20 segundos y procede a realizar la manipulación de los cubos.


# **Repositorio**

En el siguiente [repositorio](https://github.com/vbarcena2020/abitobot) se encuentra todo el paquete de ROS2 del robot Abitobot. En este se definen los URDF del robot, los launchers y todo lo utilizado para la realización de la práctica.

Esta es la [carpeta](https://github.com/vbarcena2020/abitobot/tree/main/rosbag) donde se encuentra el rosbag utilizado para la obtención y analisis de los datos.

# **Videos**

**Pick and Place video**
<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3_uvngyzkSI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br>