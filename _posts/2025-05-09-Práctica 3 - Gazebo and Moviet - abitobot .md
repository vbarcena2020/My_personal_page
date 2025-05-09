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
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/effort-time.png?raw=true" width="50%">
</p>

En cuanto al gasto parcial frente al tiempo de los joints involucrados en la cinematica inversa se puede apreciar que:

- Al comienzo el gasto es minimo hasta los casi 40 segundos debido a que en ese periodo el robot solo se encuentra aproximandose al cubo por lo tanto el unico gasto que se aprecia es el esfuerzo por no moverse los joints durante el desplazamiento.

- Luego se aprecia un gran esfuerzo producido por el movimiento y levantamiento del cubo.

- Por ultimo se aprecia un mayor esfuerzo aun cuando el brazo baja el cubo para dejarlo. En cuanto lo deja el esfuerzo vuelve a ser casi minimo.

Todo este gran cambio en el esfuerzo del brazo se debe al peso añadido del cubo. Este porvoca que se deba hacer más fuerza para llegar a las poses requeridas.

## Posición ruedas Joint_States - Tiempo


<p align="center">
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/pose-time.png?raw=true" width="50%">
</p>


En cuanto a la posición de las ruedas del robot frente al tiempo se puede apreciar que:

- Las ruedas se desplazan hasta que llegan a la posición frente a la caja a los casi 20 segundos y se mantienen en dicha posición hasta que se detiene el proceso debido a que no se mueve más el robot.

## Aceleracion Imu - Tiempo

<p align="center">
  <img src="https://github.com/vbarcena2020/My_personal_page/blob/master/assets/images/acceleration-time.png?raw=true" width="50%">
</p>

En cuanto a la aceleración frente al tiempo de los datos obtenidos de la Imu se puede apreciar que:

- Solo hay aceleración linear desde que el robot empieza a andar hasta que este procede a frenar frente al cubo a los casi 20 segundos.

# **Repositorio**

En el siguiente [repositorio](https://github.com/vbarcena2020/abitobot) se encuentra todo el paquete de ROS2 del robot Abitobot. En este se definen los URDF del robot, los launchers y todo lo utilizado para la realización de la práctica.

Esta es la [carpeta](https://github.com/vbarcena2020/abitobot/tree/main/rosbag) donde se encuentra el rosbag utilizado para la obtención y analisis de los datos.

# **Videos**

**Pick and Place video**
<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3_uvngyzkSI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
<br>