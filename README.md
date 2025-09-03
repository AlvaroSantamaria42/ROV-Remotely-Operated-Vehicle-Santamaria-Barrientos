# ROV para inspección subacuatica: Santamaria-Barrientos

![Ilustracion ROV 2 0](https://github.com/user-attachments/assets/abd9f6db-ba5b-4851-94f9-f922b9409b70)

El presente proyecto consiste en el diseño y construcción de un ROV (Remotely Operated Vehicle) para inspección subacuática, orientado a aplicaciones industriales, ambientales y científicas. Este prototipo busca ofrecer una alternativa segura y económica al uso de buzos profesionales en tareas de inspección de estructuras como represas, puertos y cascos de barcos, reduciendo costos operativos y riesgos para la vida humana.

El ROV será un sistema modular, equipado con propulsión eléctrica, cámara de transmisión en vivo y sensores de temperatura, presión y orientación, controlado en tiempo real desde la superficie mediante un tether Ethernet. Su desarrollo integra disciplinas de mecánica, electrónica y software, fomentando la aplicación práctica de conocimientos en ingeniería mecatrónica.

La propuesta apunta a lograr un prototipo funcional probado en pileta, capaz de adaptarse a distintos entornos de trabajo y de servir como base para futuras mejoras, como la incorporación de sensores adicionales o interfaces gráficas de telemetría.

\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage{geometry}
\usepackage{longtable}
\usepackage{array}
\usepackage{enumitem}

\geometry{margin=2cm}

\begin{document}

\section{Alcance}

\subsection{Prototipo funcional}
Desarrollo de un ROV con:
\begin{itemize}[label=--]
    \item 4 thrusters para movimiento en 4 GDL.
    \item Cámara + iluminación LED.
    \item Sensores básicos de profundidad, IMU y temperatura.
    \item Control mediante PC.
\end{itemize}

\subsection{Presentación del proyecto}
\textbf{Construcción:}
\begin{itemize}[label=--]
    \item Dimensiones ROV aproximadas: $40 \times 30 \times 25 \ \text{cm}$.
    \item Centro de gravedad: céntrico y ligeramente por debajo.
\end{itemize}

\textbf{Propulsores:}
\begin{itemize}[label=--]
    \item Dos horizontales en la parte trasera, simétricos respecto al eje longitudinal, montados a la misma altura, orientados paralelos al eje $X$.
    \item Dos verticales: uno delantero y otro trasero, montados para generar momento nulo en la guiñada si se suman iguales, pero con separación longitudinal para generar cabeceo si hiciera falta.
\end{itemize}

\textbf{Grados de libertad resultantes:}
\begin{itemize}[label=$\bullet$]
    \item Surge (adelante/atrás)
    \item Heave (subir/bajar)
    \item Yaw (guiñada)
    \item Pitch (cabeceo)
\end{itemize}

\subsection{Inspección y análisis de imágenes}
\begin{itemize}[label=$\bullet$]
    \item El operador en superficie visualizará las imágenes en tiempo real desde la PC.
    \item El software permitirá capturar fotos y grabar video.
    \item Se hará un análisis visual manual por parte del operador para detectar corrosión, grietas, incrustaciones, etc.
\end{itemize}

\subsection{Prueba}
\begin{itemize}[label=$\bullet$]
    \item El prototipo se probará en pileta.
    \item El proyecto podrá presentar el 100\% del prototipo mecánico y electrónico básico.
    \item Funcionalidades avanzadas como software de telemetría dependerán de disponibilidad de presupuesto y tiempo de entrega de materiales.
\end{itemize}

\subsection{Pros}
\begin{itemize}[label=$\bullet$]
    \item Permite inspecciones seguras.
    \item Modularidad $\rightarrow$ fácil adaptación a distintas aplicaciones.
    \item Desarrollo local $\rightarrow$ costo menor que equipos importados.
    \item Capaz de integrarse con sensores científicos y ambientales.
    \item Potencial para aplicaciones industriales, investigación, acuicultura, seguridad y defensa.
\end{itemize}

\subsection{Aplicación}
\begin{itemize}[label=$\bullet$]
    \item Industria: represas, puertos, astilleros, pisciculturas.
    \item Ciencia: monitoreo ambiental, arqueología submarina, análisis de biodiversidad.
\end{itemize}

\section{Especificación de Requerimientos}
\begin{itemize}[label=$\bullet$]
    \item Autonomía mínima: 30 min.
    \item Profundidad máxima operativa: 10 m.
    \item Cámara con transmisión en vivo.
    \item Sensado de temperatura, presión y orientación.
    \item Modularidad para incorporar sensores adicionales.
    \item Seguridad eléctrica con fusibles y protecciones.
\end{itemize}

\section{Diseño Funcional a Nivel Macro}
El sistema se compone de los siguientes bloques principales:
\begin{itemize}[label=$\bullet$]
    \item Propulsión: 4 motores brushless con ESC.
    \item Control y procesamiento: Raspberry Pi para software de visión y control.
    \item Sensado: IMU, sensor de presión, temperatura.
    \item Comunicación: tether Ethernet con alimentación.
    \item Carcasa: estructura impermeable con compartimientos para electrónica y baterías.
\end{itemize}

\subsection{Detalle de subsistemas}

\textbf{Electrónica y control}
\begin{itemize}[label=$\bullet$]
    \item Fuente de alimentación estable $\rightarrow$ La Raspberry Pi y los servos necesitan 5 V; los motores brushless requieren su propia fuente y ESCs.
    \item Distribución de energía $\rightarrow$ baterías Li-ion/LiPo con capacidad suficiente para 30 min de operación.
    \item Protectores y fusibles $\rightarrow$ placa de distribución de energía.
    \item Controladores de motores $\rightarrow$ fusibles para cada línea de potencia.
\end{itemize}

\textbf{Sensores}
\begin{itemize}[label=$\bullet$]
    \item IMU 6050: orientación y aceleración.
    \item Sensor de presión GY-MS5837-30BA: profundidad.
    \item DS18B20: temperatura del agua o electrónica.
    \item Sensores opcionales: magnetómetro, medidor de pH, conductividad del agua.
\end{itemize}

\textbf{Actuadores}
\begin{itemize}[label=$\bullet$]
    \item Servos para cámara: movimiento vertical.
    \item Motores brushless: propulsión.
    \item Motor paso a paso/servo: mecanismos de agarre.
\end{itemize}

\textbf{Comunicaciones}
\begin{itemize}[label=$\bullet$]
    \item Ethernet $\rightarrow$ transmisión de video y control en tiempo real al PC.
\end{itemize}

\textbf{Carcasa y mecánica}
\begin{itemize}[label=$\bullet$]
    \item Cuerpo impermeable para Raspberry Pi, baterías y drivers.
    \item Soportes para servos y cámara.
    \item Ejes y hélices protegidos.
    \item Flotación y lastre $\rightarrow$ estabilidad del ROV bajo agua.
\end{itemize}

\textbf{Software}
\begin{itemize}[label=$\bullet$]
    \item Python $\rightarrow$ visión y procesamiento de video.
    \item Control de motores y servos $\rightarrow$ GPIO.
    \item Telemetría $\rightarrow$ lectura de sensores y envío al PC.
    \item Interfaz gráfica opcional $\rightarrow$ mostrar cámara y datos en tiempo real.
\end{itemize}

\section{Detalle Preliminar de Pines del Microcontrolador}
Se utilizará una Raspberry Pi combinada con controladores externos:
\begin{itemize}[label=$\bullet$]
    \item 4 salidas PWM para control de ESC de motores.
    \item 2 salidas PWM para servos de cámara.
    \item 2 entradas digitales para sensores de temperatura.
    \item 1 entrada I2C para IMU.
    \item 1 entrada I2C/SPI para sensor de presión.
    \item 1 puerto UART para expansión.
\end{itemize}

En el mercado, equipos comerciales similares (BlueROV2, VideoRay) superan los USD 4.000–10.000, lo que muestra que el desarrollo local es al menos 10 veces más económico. Los plazos de entrega dependerán principalmente de componentes importados ($\sim$30 días).

\section{Costos del Prototipo y Proveedores}
\begin{longtable}{|>{\raggedright}m{5cm}|c|c|c|}
\hline
\textbf{Componentes} & \textbf{Cantidad} & \textbf{ARS} & \textbf{Dólares} \\
\hline
Placa Raspberry Pi 5 4GB & 1 & 107.254,00 & 79,4 \\
Memoria micro SD 64GB U3 DUAITEK & 1 & 11.070 & 8,2 \\
Cámara & 1 & 20.000 & 14,8 \\
Sensor de Temperatura DS18B20 & 1 & 2.072 & 1,5 \\
Acelerómetro y Giroscopio MPU-6050 & 1 & 3.198,00 & 2,4 \\
Sensor de Temperatura y humedad HTU21D & 1 & 3.567,00 & 2,6 \\
Sensor de presión GY-MS5837-30BA & 1 & 18.000 & 13,3 \\
Servo Tower Pro SG90 9g & 2 & 5.460,00 & 4,0 \\
Motor Brushless A2212 930kv & 4 & 60.000 & 44,4 \\
ESC 20/30A para brushless & 4 & 40.000 & 29,6 \\
Propulsor 3 aspas & 4 & 10.000 & 7,4 \\
Cable Ethernet (10 metros) & 1 & 10.000 & 7,4 \\
Conector Mini-DIN 8 pines & 1 & 4.000 & 3,0 \\
Chasis, carcasa y sellado & 1 & 20.000 & 14,8 \\
\hline
\textbf{TOTAL} & -- & 314.621 & 232,8 \\
\hline
\end{longtable}

\section{Presupuestos y Comparativa}
En el mercado, equipos comerciales similares (BlueROV2, VideoRay) superan los USD 4.000–10.000, lo que muestra que el desarrollo local es al menos 10 veces más económico. Los plazos de entrega dependerán principalmente de componentes importados ($\sim$30 días).

\section{Cronograma de Trabajo}
\textbf{Primera entrega (22/09/25):}
\begin{itemize}[label=$\bullet$]
    \item Funcionamiento de sensores por separado con su software.
    \item Funcionamiento de los motores por separado con su software.
    \item Creación de los circuitos que integren los 4 motores junto con el control de ambos 4.
    \item Software que integre todos los sensores en simultáneo.
\end{itemize}

\textbf{Segunda entrega (20/10/25):}
\begin{itemize}[label=$\bullet$]
    \item Chasis armado con sus motores y sensores integrados, junto con una versión de prueba de control y cámara.
\end{itemize}

\textbf{Entrega final (17/11/25):}
\begin{itemize}[label=$\bullet$]
    \item ROV terminado con el software funcionando, sensando y controlando remotamente el dron mientras transmite en vivo por cámara.
\end{itemize}

\end{document}

