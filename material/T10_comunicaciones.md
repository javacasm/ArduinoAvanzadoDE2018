
## Comunicaciones Serie

El protocolo de comunicaciones más sencillo es que ya hemos usado: el protocolo serie.

La forma natural de comunicarse con Arduino es utilizando el puerto serie, siendo este el método de depuración más usado.
En el [siguiente vídeo](https://youtu.be/A6BH4cfqS4k) veremos detalles sobre este protocolo, cómo usarlo en Arduino y cómo leer datos desde Arduino.

Actualización: en el vídeo no aparecen los métodos readString y readStringUntil, muy útiles de la librería Serial. Nos facilitan enormemente el recuperar cadena desde el puerto serie.

Os dejo una presentación donde se trata en más detalle "Tema 10 - Comunicaciones serie.pdf"


## Comunicaciones bluetooth


## Procotocolos de comunicaciones

En el [siguiente vídeo](https://www.youtube.com/embed/DePCak9WNPM) hablaremos sobre algunos de los protocolos de comunicaciones más usados, como son I2C y SPI.

La presentación está disponible en el fichero "Tema 10 - Protocolos de comunicaciones.pdf"

### Pines SPI


¿Dónde están los pines SPI en las distintas placas?

![Pines SPI](./images/SPI_pines.png)

Uno de los protocolos de comunicaciones más usados en Arduino es el SPI. Se utiliza para comunicarse con multitud de dispositivos. Cómo norma general, la manera más sencilla de encontrar los pines SPI es en el conector ICSP. Algunas placas los duplican entre los pines digitales, pero otras no.

|Placa| SCK|MOSI|MISO
|---|---|---|---
|Arduino UNO|D13|D11|D12
|Arduino Leonardo|D3|D4|D1
|Arduino Mega|D52|D51|D50
