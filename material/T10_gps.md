## Uso del GPS

Un GPS no es más que un dispositivo que recibe señales de los satélites GPS, las procesa para obtener información sobre la posición y las envía (tramas NMEA) por un puerto de comunicaciones, normalmente vía puerto serie.

Su conexión es muy sencilla pues basta con alimentarlo y conectar sus pines Tx y Rx a Arduino y hacer un programa que lea las tramas.

![https://i1.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/01/NEO_6M_Arduino.png?resize=1024%2C551&ssl=1](https://i1.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/01/NEO_6M_Arduino.png?resize=1024%2C551&ssl=1)

En el programa usaremos la librería SoftwareSerie para poder usar otros pines de Arduino

    /*
     * Rui Santos
     * Complete Project Details http://randomnerdtutorials.com
     */

    #include <SoftwareSerial.h>

    // The serial connection to the GPS module
    SoftwareSerial ss(4, 3);

    void setup(){
      Serial.begin(9600);
      ss.begin(9600);
    }

    void loop(){
      while (ss.available() > 0){
        // get the byte data from the GPS
        byte gpsData = ss.read();
        Serial.write(gpsData);
      }
    }

Hay que recordar que los receptores GPS (y sobre todo los baratos) tardan un tiempo en conseguir suficientes señales de los satélites y necesitan de un espacio abierto para que estas lleguen.

Cuando empiecen a recibirse tramas serán algo así:


      $GPGGA,140817.00,4105.2344,N,00831.54761,W,1,05,2.68,129.0,M,50.1,M,,*42
      $GPGSA,A,3,06,09,30,07,23,,,,,,,,4.43,2.68,3.53*02
      $GPGSV,3,1,11,02,48,298,24,03,05,101,24,05,17,292,20,06,71,227,30*7C

Que nos informa de la posición, altura, etc... Por ejemplo la primera línea nos dice

* Hora de la señal 14:08:17
* Latitud 4105.2344,N
* Longitud 831.54761,W

Podemos procesar estos datos usando librerías por ejemplo TinyGPSPlus

### Referencias

Para aprender más sobre GPS os recomiendo [el artículo de Rui Santos](https://randomnerdtutorials.com/guide-to-neo-6m-gps-module-with-arduino/) del que saqué la información
