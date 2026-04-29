<img width="1914" height="408" alt="image" src="https://github.com/user-attachments/assets/ea276535-1afb-491d-a723-c80aa9b4b952" />
```
## INTRODUCCIÓN

#### Esta práctica documenta la implementación de un ecosistema IoT basado en el microcontrolador ESP32, orientado a la adquisición de datos, conectividad inalámbrica y visualización remota de parámetros. El sistema integra el procesamiento de señales analógicas, la gestión de redes mediante protocolos TCP/IP y la transmisión de información bajo el estándar MQTT, permitiendo la supervisión técnica de variables en tiempo real.
```
### Imagen de Reto 1: Adquisición de datos

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/3273e554-44ed-4b05-a665-b6d124f8e14d" />

#### Imagen de código ejecutándose del primer reto: Encender un led y cambiar su intensidad con ayuda del potenciómetro

<img width="1600" height="890" alt="image" src="https://github.com/user-attachments/assets/e1e6f9a0-9225-4150-93c6-5608722d0b69" />

#### Imagen del led prendiéndose:

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/661efe3a-e777-44cf-b84a-9b81d57d4a77" />

#### Imagen del led anexado al código fuente:

````
const int potPin = 34;
const int ledPin = 2;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int valorPot = analogRead(potPin);  // 0 a 4095

  // Mapea de 0-4095 a 0-255
  int brillo = map(valorPot, 0, 4095, 0, 255);

  analogWrite(ledPin, brillo);  // PWM proporcional

  Serial.print("Potenciometro: ");
  Serial.print(valorPot);
  Serial.print(" | Brillo: ");
  Serial.println(brillo);

  delay(100);
}

````

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/f40129fc-74ad-4cfa-bad8-9ca76484f51a" />



### Imagen de Reto 2: Conexión de red /Internet Esp32

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/383b9ee6-4282-4a1a-8a01-ae536b2c3b56" />


#### Imagen de las redes que aparecieron a raíz de compilar el código:

<img width="1600" height="847" alt="image" src="https://github.com/user-attachments/assets/dbf5c651-2a38-46b7-b2df-eaa09a6d6acd" />


### Imagen de Reto 3: 

<img width="1279" height="639" alt="image" src="https://github.com/user-attachments/assets/3fb14f74-d94c-4ff9-b51e-774b375ca020" />

#### Imagen de la aplicación MQTTX, inicializando el mensaje en la conexión Taller-IOT:


<img width="569" height="830" alt="image" src="https://github.com/user-attachments/assets/8e3863cb-9bc9-47b0-9b05-de836c0952c6" />



#### Imagen de código de configuración que  realizar en el nodo función:

<img width="814" height="746" alt="image" src="https://github.com/user-attachments/assets/eac896e8-b7d7-4678-9a04-25dfad65dc00" />


#### Imagen de la primera configuración exitosa mostrando en pantalla del dashboard la temperatura 20.5°C:

````
{
  "temp": "20.5"
}

````

<img width="1600" height="774" alt="image" src="https://github.com/user-attachments/assets/96b9404f-7cd5-4d6c-a3bd-5543dd3757cb" />

#### Imagen de la aplicación MQTTX, inicializando el mensaje en la conexión Taller-IOT con el nuevo código:


````
{
  "temp": "80.99"
}

````

<img width="1228" height="1022" alt="image" src="https://github.com/user-attachments/assets/f7529990-8b5e-47e4-b722-c2c8e0520ce9" />



#### Imagen de nueva configuración exitosa mostrando en pantalla del dashboard la temperatura 80.99°C:

<img width="1600" height="739" alt="image" src="https://github.com/user-attachments/assets/b19afdf7-1930-475f-9697-53e593f04250" />


### Resultados


A continuación, se expresa la caracterización del sistema IoT detallada en los resultados obtenidos:

El sistema de adquisición de datos registró una resolución de cuantización de 12 bits, correspondiente a un rango de entrada de $0$ a $4095$ unidades enteras procesadas por el convertidor analógico-digital (ADC) del microcontrolador. Estos valores fueron transformados mediante un algoritmo de mapeo lineal en un ciclo de trabajo para modulación por ancho de pulsos (PWM) con una resolución de 8 bits ($0$ a $255$), manteniendo una proporcionalidad directa en la salida de voltaje del pin GPIO 2.

Durante las pruebas de conectividad en la banda de 2.4 GHz, el dispositivo identificó y listó la totalidad de los identificadores de conjunto de servicios (SSID) disponibles en el área de cobertura, validando la operatividad de la capa física y de enlace. 

En la fase de telemetría, se verificó el procesamiento de tramas de datos en formato JSON mediante el protocolo MQTT, alcanzando una precisión de transmisión de dos cifras decimales (e.g., $80.99$). La latencia observada entre la inyección del mensaje en el cliente MQTTX y la actualización del valor en el dashboard de Node-RED se mantuvo dentro de los parámetros de tiempo real para monitoreo industrial, sin registrarse pérdida de paquetes ni errores de integridad en la carga útil (payload) durante las iteraciones de prueba programadas.
