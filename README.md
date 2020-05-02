# incubator
sensing temperature in a specific environment

--- german:
Das Ziel ist die Umgebungsmessung anhand der Temperatur und Luftfeuchte, um für konstante 30 Grad Celsius in einem abgegrenzten Bereich zu sorgen. In diesem Bereich sind Arbeitsmittel aufbewahrt, welche diese konstante Temperatur benötigen.

Es wird mit Hilfe von 3x BME280 von AZ-Delivery bei identischer I2C Adresse die Umgebungs-Werte abgerufen und auf einem LCD Display 2004A zur Anzeige gebracht. Die Komplexität liegt nun darin:
a.) Management der idetischen I2C Adressen einem I2C Multiplexer zu überlassen (Adafruit #2717: TCA9548A switcht jeweils auf den Sensor-Kanal um)
b.) auch im Bereich selbst ist nochmals ein Gehäuse für ein Arbeitsmittel untergebracht, welches seinen eigenen Temperaturfühler mitbringt. Zur Überprüfung dieser Kalibrierung wird ein BME280 mit in das Gehäuse eingebracht, welcher seine Werte via 433 MHz Radio Modul an den Empfänger weiterleitet. Hierbei musste darauf eingegangen werden, wie die Daten vom Typ char (für die Radio-Übermittlung) übertragen und wieder vom Typ float ausgegeben werden.

Je nach Temperatur-Erhebung wird dann ein entsprechendes Relay angesprochen, entweder eine Heizung oder eine Kühlung anzusteuern. Hierauf wird im Einzelnen nicht eingegangen.

--- english:
The goal is to measure the environment based on temperature and humidity in order to ensure a constant 30 degrees Celsius in a defined area. Work equipment that needs this constant temperature is stored in this area.

With the help of 3x BME280 from AZ-Delivery with identical I2C address the environmental values are called up and displayed on an LCD display 2004A. The complexity is now:
a.) Leave management of the identical I2C addresses to an I2C multiplexer (Adafruit # 2717: TCA9548A switches to the sensor channel)
b.) Also in the area itself is a housing for a work equipment that brings its own temperature sensor. To check this calibration, a BME280 is inserted into the housing, which transmits its values to the receiver via a 433 MHz radio module. Here it had to be considered how the data of the char type (for radio transmission) was transmitted and how it was output again of the float type.

Depending on the temperature measurement, a corresponding relay is then activated to control either heating or cooling. This will not be dealt with in detail.
