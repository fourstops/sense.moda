## sense.moda

*a Prometheus exporter variety pack*
<br>
<br>

   Sensor   | Metric                                                                             
| :--------: | :----------------------------------------------------------------------------------- |
| *CCS811*  | Total Volatile Organic Compounds (TVOCs), including equivalent carbon dioxide (eCO2)  |
|  *BME680*  | Temperature, Relative Humidity. Pressure, VOCs                                       |
| *PZEM-016* | AC Volts, Amps, Watts, kWh, Hertz, Power Factor                                      |
|  *SDS011*  | PM2.5, PM10                                                                          |
<br>
<br>


*   ***Dependencies***
```bash
git clone https://github.com/fourstops/sense.moda
cd sense.moda

pip install prometheus-client
pip install paho-mqtt
pip install python-pzem
pip install py-sds011
pip install aqipy
pip install adafruit-circuitpython-ccs811
pip install adafruit-circuitpython-sgp40
pip install adafruit-circuitpython-bme680
```

*   **pzem016\_exporter module**

```bash
cd  ~/sense.moda
sudo cp -r pzem016_exporter /usr/src/
sudo chown -R pi:pi /usr/src/pzem016_exporter

cd /usr/src/pzem016_exporter
sudo cp ~/stemma/services/pzem016-exporter.service /etc/systemd/system/pzem016-exporter.service
sudo chmod 644 /etc/systemd/system/pzem016-exporter.service
sudo systemctl daemon-reload

sudo systemctl start pzem016-exporter

sudo systemctl status pzem016-exporter

sudo systemctl enable pzem016-exporter

```

*   **sds011\_exporter module**

```bash
cd  ~/sense.moda
sudo cp -r sds011_exporter /usr/src/
sudo chown -R pi:pi /usr/src/sds011_exporter

cd /usr/src/sds011_exporter
sudo cp ~/stemma/services/sds011-exporter.service /etc/systemd/system/sds011-exporter.service
sudo chmod 644 /etc/systemd/system/sds011-exporter.service
sudo systemctl daemon-reload

sudo systemctl start sds011-exporter

sudo systemctl status sds011-exporter

sudo systemctl enable sds011-exporter
```
<br>

*   **stemma\_exporter module**

```bash
cd  ~/sense.moda
sudo cp -r stemma_exporter /usr/src/
sudo chown -R pi:pi /usr/src/stemma_exporter

cd /usr/src/stemma_exporter
sudo cp ~/stemma/services/stemma-exporter.service /etc/systemd/system/stemma-exporter.service
sudo chmod 644 /etc/systemd/system/stemma-exporter.service
sudo systemctl daemon-reload

sudo systemctl start stemma-exporter

sudo systemctl status stemma-exporter

sudo systemctl enable stemma-exporter


```
