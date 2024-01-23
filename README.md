# PRACTICA-N2
Este repositorio muestra como podemos programar una tarjeta  ESP32 con el sensor DHT22.
## Introducción
### Descripción
La ```Esp32``` la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (```DTH22```) para adquirir temperatura y humedad del entorno; Cabe aclarar que esta practica se usara un simulador llamado [WOKWI](https://https://wokwi.com/).

## Material Necesario
Para realizar esta practica necesitas lo siguiente
- [WOKWI](https://https://wokwi.com/)
- Tarjeta ESP 32
- Sensor DHT22

## Instrucciones
### Requisitos previos
Para poder usar este repositorio necesitas entrar a la plataforma [WOKWI](https://https://wokwi.com/).

### Instrucciones de preparación de entorno 
1. Abrir la terminal de programación y colocar la siguente programación:

```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
```
2. Instalar la libreria de **DHT sensor library for ESPx**.
   - Seleccionar pestaña de Librery Manager --> Add a New library --> Colocamos el nombre de libreria

  ![](https://github.com/DanielX834/PRACTICA-N2/blob/main/1Libreria.jpg?raw=true)
  
3. Hacer la conexion de **DHT22** con la **ESP32** como se muestra en la siguente imagen.
![](https://github.com/DanielX834/PRACTICA-N2/blob/main/2Conexion.jpg?raw=true)

### Instrucciónes de operación

1. Iniciar simulador.
2. Visualizar los datos en el monitor serial.
3. Colocar la temperatura y humedad dando *doble click* al sensor **DHT22**

## Resultados

Una vez terminado iniciamos simulacion y se observaran los valores dentro del monitor serial.


