# 🤖 Diseño de un Controlador Fuzzy para Guiado de un Robot Móvil

## 📝 Resumen

Este proyecto consiste en el desarrollo de un **controlador Fuzzy de tipo Mamdani** para guiar un robot móvil, **Amigobot**, en entornos desconocidos. El objetivo principal es evitar obstáculos y optimizar las trayectorias del robot mediante el uso de reglas basadas en heurística y datos de sensores ultrasónicos.

![Robot Amigobot](images/amigobot.png)

## 📑 Tabla de Contenidos
- [🔍 Introducción](#introducción)
- [🚘 Características del Robot](#características-del-robot)
- [🎛️ Diseño del Controlador Fuzzy](#diseño-del-controlador-fuzzy)
  - [⚙️ Entradas y Salidas](#entradas-y-salidas)
  - [📊 Conjuntos Borrosos](#conjuntos-borrosos)
  - [📜 Reglas del Controlador](#reglas-del-controlador)
- [🧪 Simulación y Resultados](#simulación-y-resultados)
- [🔚 Conclusiones](#conclusiones)
- [📚 Referencias](#referencias)

## 🔍 Introducción

La robótica móvil ha experimentado un gran avance, tanto en la academia como en la industria. Este trabajo se enfoca en el diseño de un controlador **Fuzzy** para guiar un robot en entornos desconocidos, permitiendo que este evite obstáculos y optimice sus movimientos. El controlador fue simulado en el entorno **Player Stage** y probado con éxito en un robot real.

## 🚘 Características del Robot

- **🤖 Robot**: Amigobot
- **🔊 Sensores**: 6 sensores ultrasónicos frontales con un alcance de hasta 4 metros.
- **🏎️ Velocidad Máxima**: 0.9 m/s
- **🛞 Sistema de Tracción**: Diferencial
- **🌐 Control**: Se realiza a través de una conexión LAN, con odometría para determinar la posición relativa del robot.

![Sensores del Amigobot](images/sensores.png)

## 🎛️ Diseño del Controlador Fuzzy

### ⚙️ Entradas y Salidas
- **Entradas**:
  1. 🔄 Distancia medida por el sensor frontal izquierdo.
  2. 🔄 Distancia medida por el sensor frontal derecho.
  3. ⚖️ Diferencia entre sensores laterales.
  4. ⚖️ Diferencia entre sensores esquineros.
  
- **Salidas**:
  1. 🏎️ Velocidad lineal.
  2. 🔄 Velocidad angular.

### 📊 Conjuntos Borrosos

Los conjuntos borrosos para las entradas y salidas están diseñados con funciones trapezoidales y triangulares que permiten definir con precisión las decisiones del controlador. Los subconjuntos se agrupan en categorías como **Pequeño**, **Medio**, y **Grande** para las entradas de distancia, mientras que para las salidas se definen niveles de velocidad y dirección.

### 📜 Reglas del Controlador

El conjunto de reglas Fuzzy está compuesto por **26 combinaciones** diseñadas heurísticamente para que el robot evite obstáculos mientras mantiene una velocidad adecuada. Algunas reglas incluyen:

- **Regla 1**: Si el robot detecta un obstáculo cerca por los dos sensores frontales, reduce la velocidad y gira.
- **Regla 2**: Si no hay obstáculos, incrementa la velocidad lineal y avanza.

## 🧪 Simulación y Resultados

La simulación se llevó a cabo en el entorno **Player Stage**, donde el robot fue capaz de navegar eficientemente por mapas con diferentes obstáculos, sin colisionar con ningún objeto. A continuación, se muestran algunas imágenes de los recorridos simulados:

![Simulación Mapa 1](images/simulacion_mapa1.png)
![Simulación Mapa 2](images/simulacion_mapa2.png)

En los ensayos reales, el **Amigobot** evitó objetos grandes y realizó el trayecto sin colisiones. Las pruebas fueron satisfactorias y demostraron la capacidad del controlador en un entorno real.

## 🔚 Conclusiones

El **controlador Fuzzy** implementado permite la navegación eficiente de un robot móvil en entornos desconocidos, evitando obstáculos con éxito. Se concluye que:

- El uso de sistemas **MIMO** con controladores Fuzzy es una opción efectiva.
- La simplicidad del **control Mamdani** lo hace adecuado para aplicaciones de tiempo real.
- El controlador puede implementarse en sistemas de procesamiento más avanzados como ARM o Core 2 Duo.

## 📚 Referencias

1. A. Aksamovic, M. Hebibovic, y S. Konjicija, «Similarities in development of digital computers and mobile robots», IEEE EUROCON 2009.
2. H. Fukai, Y. Mitsukura, y G. Xu, «The calibration between range sensor and mobile robot», 2012 IEEE RO-MAN.
3. A. R. Willms y S. X. Yang, «An efficient dynamic system for real-time robot-path planning», IEEE Trans. Syst. Man Cybern. Part B Cybern., vol. 36, n.o 4, 2006.
4. X. Lai, S. Zhu, y W. Wu, «Research on driving wheel control of cleaning robot based on fuzzy adaptive tuning PID», International Conference on Mechatronics and Automation, 2009.
5. S. H. Lian, «Fuzzy logic control of an obstacle avoidance robot», Fifth IEEE International Conference on Fuzzy Systems, 1996.

---

© 2024. Todos los derechos reservados.
