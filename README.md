## go-to-prom

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
git clone https://github.com/fourstops/go-to-prom
cd go-to-prom

pip install prometheus-client
pip install paho-mqtt
pip install python-pzem
pip install py-sds011
pip install aqipy
pip install smbus
pip install adafruit-circuitpython-ccs811
pip install adafruit-circuitpython-sgp40
pip install adafruit-circuitpython-bme680
```

*   **pzem016\_exporter module**

```bash
cd  ~/go-to-prom
sudo cp -r pzem-exporter /usr/src/
sudo chown -R pi:pi /usr/src/pzem-exporter
sudo chmod 666 /dev/ttyAMA0

cd /usr/src/pzem-exporter
sudo cp ~/go-to-prom/services/pzem-exporter.service /etc/systemd/system/pzem-exporter.service
sudo chmod 644 /etc/systemd/system/pzem-exporter.service

sudo systemctl daemon-reload

sudo systemctl start pzem-exporter

sudo systemctl status pzem-exporter

sudo systemctl enable pzem-exporter

```

*   **sds011\_exporter module**

```bash
cd  ~/go-to-prom
sudo cp -r sds011_exporter /usr/src/
sudo chmod -R 775 /usr/src/sds011_exporter
sudo chown -R pi:pi /usr/src/sds011_exporter

cd /usr/src/sds011_exporter

sudo cp ~/go-to-prom/services/sds011-exporter.service /etc/systemd/system/sds011-exporter.service

sudo cp ~/go-to-prom/services/sds011-exporter.service /etc/systemd/system/sds011-exporter.service

sudo chmod 644 /etc/systemd/system/sds011-exporter.service
sudo systemctl daemon-reload

sudo systemctl start sds011-exporter

sudo systemctl status sds011-exporter

sudo systemctl enable sds011-exporter
```
<br>

*   **moda\_exporter module**

```bash
cd  ~/go-to-prom
sudo cp -r stemma-exporter /usr/src/
sudo chown -R pi:pi /usr/src/go-to-prom_exporter

cd /usr/src/go-to-prom_exporter
sudo cp ~/go-to-prom/services/go-to-prom-exporter.service /etc/systemd/system/go-to-prom-exporter.service
sudo chmod 644 /etc/systemd/system/go-to-prom-exporter.service

cd /usr/src/stemma-exporter
sudo cp ~/go-to-prom/services/stemma-exporter.service /etc/systemd/system/stemma-exporter.service
sudo chmod 644 /etc/systemd/system/stemma-exporter.service

sudo systemctl daemon-reload

sudo systemctl start moda-exporter

sudo systemctl status moda-exporter

sudo systemctl enable moda-exporter


```
