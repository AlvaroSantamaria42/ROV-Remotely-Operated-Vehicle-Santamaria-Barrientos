# ROV para inspección subacuatica: Santamaria-Barrientos

![Ilustracion ROV 2 0](https://github.com/user-attachments/assets/abd9f6db-ba5b-4851-94f9-f922b9409b70)

El presente proyecto consiste en el diseño y construcción de un ROV (Remotely Operated Vehicle) para inspección subacuática, orientado a aplicaciones industriales, ambientales y científicas. Este prototipo busca ofrecer una alternativa segura y económica al uso de buzos profesionales en tareas de inspección de estructuras como represas, puertos y cascos de barcos, reduciendo costos operativos y riesgos para la vida humana.

El ROV será un sistema modular, equipado con propulsión eléctrica, cámara de transmisión en vivo y sensores de temperatura, presión y orientación, controlado en tiempo real desde la superficie mediante un tether Ethernet. Su desarrollo integra disciplinas de mecánica, electrónica y software, fomentando la aplicación práctica de conocimientos en ingeniería mecatrónica.

La propuesta apunta a lograr un prototipo funcional probado en pileta, capaz de adaptarse a distintos entornos de trabajo y de servir como base para futuras mejoras, como la incorporación de sensores adicionales o interfaces gráficas de telemetría.

2. Motivación y antecedentes
La inspección subacuática en represas, diques, puertos, embarcaciones y cuerpos de agua requiere actualmente el uso de buzos profesionales. Esto genera:
•	Altos costos operativos.
•	Riesgos para la vida humana.
•	Limitaciones en la profundidad y tiempo de inspección.
•	Dificultad para realizar monitoreo frecuente y sistemático.
Además, existe un mercado emergente para la observación ambiental, la acuicultura, la investigación científica y la industria naval, donde un ROV accesible y modular puede ofrecer soluciones innovadoras y más económicas.
3. Descripción de la propuesta
El proyecto consiste en diseñar y construir un prototipo de ROV modular, con capacidades de inspección visual, que permita:
•	Monitorear estructuras subacuáticas como compuertas de represas, cascos de barcos y redes de piscicultura.
•	Registrar datos ambientales (pH, temperatura, conductividad) para estudios científicos y de impacto ambiental.
•	Facilitar inspecciones seguras, reduciendo riesgos para personal humano.
•	Implementar control remoto mediante un tether basado en cable Ethernet que transporta energía y datos hacia la superficie, controlado por un PC.
Motivo de elección: se combina la complejidad mecánica, electrónica y de control, al mismo tiempo que el prototipo es viable económicamente y puede tener aplicaciones reales.
4. Alcance
Prototipo funcional: desarrollo de un ROV con:
o	4 thrusters para movimiento en 4 GDL.
o	Cámara + iluminación LED.
o	Sensores básicos de profundidad, IMU y temperatura.
o	Control mediante PC.
Presentación del proyecto:
Construcción:
Dimensiones ROV aproximada.: 40 × 30 × 25 cm.
Centro de gravedad: céntrico y ligeramente por debajo.
Propulsores:
Dos horizontales en la parte trasera, simétricos respecto al eje longitudinal, montados a la misma altura, orientados paralelos al eje X.
Dos verticales uno delantero y otro trasero, montados para generar momento nulo en la guiñada si se suman iguales, pero con separación longitudinal para generar cabeceo si hiciera falta.
RDL resultantes: 
•	Surge (adelante/atrás) 
•	Heave (subir/bajar)
•	Yaw (guiñada)
•	Pitch(cabeceo)


Inspección y análisis de imágenes
•	El operador en superficie visualizará las imágenes en tiempo real desde la PC.
•	El software permitirá capturar fotos y grabar video.
•	Se hará un análisis visual manual por parte del operador para detectar corrosión, grietas, incrustaciones, etc.
Prueba:
•	El prototipo se probará en pileta.
•	El proyecto podrá presentar el 100% del prototipo mecánico y electrónico básico.
•	Funcionalidades avanzadas como software de telemetría, dependerán de disponibilidad de presupuesto y tiempo de entrega de materiales.
Pros:
•	Permite inspecciones seguras.
•	Modularidad → fácil adaptación a distintas aplicaciones.
•	Desarrollo local → costo menor que equipos importados.
•	Capaz de integrarse con sensores científicos y ambientales.
•	Potencial para aplicaciones industriales, investigación, acuicultura, seguridad y defensa.
Aplicación:
•	Industria: represas, puertos, astilleros, pisciculturas.
•	Ciencia: monitoreo ambiental, arqueología submarina, análisis de biodiversidad.
5. Especificación de Requerimientos
•	Autonomía mínima: 30 min.
•	Profundidad máxima operativa: 10 m.
•	Cámara con transmisión en vivo.
•	Sensado de temperatura, presión y orientación.
•	Modularidad para incorporar sensores adicionales.
•	Seguridad eléctrica con fusibles y protecciones.
6. Diseño Funcional a Nivel Macro
El sistema se compone de los siguientes bloques principales:
•	Propulsión: 4 motores brushless con ESC.
•	Control y procesamiento: Raspberry Pi para software de visión y control.
•	Sensado: IMU, sensor de presión, temperatura.
•	Comunicación: tether Ethernet con alimentación.
•	Carcasa: estructura impermeable con compartimientos para electrónica y baterías.



Detalle de subsistemas:
Electrónica y control
•	Fuente de alimentación estable → La Raspberry Pi y los servos necesitan 5 V; los motores brushless requieren su propia fuente y ESCs.
•	Distribución de energía → Considerar baterías Li-ion/LiPo con capacidad suficiente para 30 min de operación.
•	Protectores y fusibles → Placa de distribución de energía para que cada componente reciba su voltaje y corriente correcta.
•	Controladores de motores → Fusibles para cada línea de potencia pueden prevenir daños si hay cortocircuitos.
Sensores
•	IMU 6050 → orientación y aceleración
•	Sensor de presión GY-MS5837-30BA → profundidad
•	DS18B20 → temperatura del agua o electrónica
•	Sensores opcionales: magnetómetro, medidor de pH, conductividad del agua.
Actuadores
•	Servos para cámara → Movimiento vertical
•	Motores brushless → propulsión
•	Motor paso a paso/servo → mecanismos de agarre.
Comunicaciones
•	Ethernet → transmisión de video y control en tiempo real al PC
Carcasa y mecánica
•	Cuerpo impermeable para Raspberry Pi, baterías y drivers
•	Soportes para servos y cámara
•	Ejes y hélices protegidos para evitar contacto con cables o agua
•	Flotación y lastre → estabilidad del ROV bajo agua
Software
•	Python → visión y procesamiento de video
•	Control de motores y servos → GPIO
•	Telemetría → lectura de sensores y envío al PC
•	Interfaz gráfica opcional → mostrar cámara y datos en tiempo real
7. Detalle Preliminar de Pines del Microcontrolador
Se utilizará una Raspberry Pi combinada con controladores externos. Se prevé:
•	4 salidas PWM para control de ESC de motores.
•	2 salidas PWM para servos de cámara.
•	2 entradas digitales para sensores de temperatura.
•	1 entrada I2C para IMU.
•	1 entrada I2C/SPI para sensor de presión.
•	1 puerto UART para expansión.
En el mercado, equipos comerciales similares (BlueROV2, VideoRay) superan los USD 4.000–10.000, lo que muestra que el desarrollo local es al menos 10 veces más económico. Los plazos de entrega dependerán principalmente de componentes importados (~30 días).
8. Costos del Prototipo y Proveedores
Componentes	Cantidad	ARS	Dolares
Placa Raspberry PI 5 4GB	1	107.254,00	79,4
Memoria micro SD 64GB U3 DUAITEK	1	11.070	8,2
Camara	1	20.000	14,8
Sensor de Temperatura DS18B20	1	2.072	1,5
Acelerómetro y Giroscopio MPU-6050	1	3.198,00	2,4
Sensor de Temperatura y humedad HTU21D	1	3.567,00	2,6
Sensor de presión GY-MS5837-30BA	1	18.000	13,3
Servo Tower Pro Sg90 9g	2	5.460,00	4
Motor Brushless A2212 930kv	4	60000	44,4
ESC 20/30A para brushless	4	40000	29,6
Propulsor 3 aspas	4	10000	7,4
Cable ethernet (10 metros)	1	10.000	7,4
Conector Mini-DIN 8 pines	1	4.000	3
Chasis, carcasa y sellado	1	20.000	14,8
TOTAL	-	314621	232.8

9. Presupuestos y Comparativa
En el mercado, equipos comerciales similares (BlueROV2, VideoRay) superan los USD 4.000–10.000, lo que muestra que el desarrollo local es al menos 10 veces más económico. Los plazos de entrega dependerán principalmente de componentes importados (~30 días).
10. Cronograma de Trabajo
Primera entrega (22/09/25):
Funcionamiento de sensores por separado con su software.
Funcionamiento de los motores por separado con su software.
Creación de los circuitos que integren los 4 motores junto con el control de ambos 4.
Software que integre todos los sensores en simultaneo.
Segunda entrega (20/10/25):
Chasis armado con sus motores y sensores integrados, junto con una versión prueba de control y cámara.
Entrega final (17/11/25):
ROV terminado con el software funcionando, sensando y controlando remotamente el dron mientras transmite en vivo por cámara.
