![giphy](https://user-images.githubusercontent.com/105724334/204540288-45ba24a5-faeb-46c9-960d-9073b0f2f7e6.gif)
###### Rain Weather GIF By Hey Duggee [^5]

# Unit 2: A Distributed Weather Station for ISAK

## Criteria A: Planning

### Problem definition
An IB student got recently diagnosed with depression and is currently taking medication for it. The medication that was prescribed must be kept under tedious circumstances such as certain humidity and temperature levels the student is afraid the environment they live in will not meet. In order to decide the next step, whether that is buying a medicine chamber that is pricey, they must measure the humidity and temperatures of their room. The student is looking for an affordable yet accurate method of doing so. They have asked the computer science students Mayte and Yasmina to gather accurate data and create graphs that compare and determine the humidity levels and temperatures in the student’s room as well as outside. This is because drugs can increase one’s sensitivity to heat and humidity, therefore they need to be carefully calculated to avoid future health issues[^6]. This experiment will help the student live a healthy life regardless of depression!

### Proposed Solution
Considering the client's requirements, an adequate solution includes a low-cost sensing device for humidity and temperature and a custom data script that process and analyzes the samples acquired. For a low-cost sensing device, an adequate alternative is the DHT11 sensor[^1] which is offered online for less than 5 USD and provides adequate precision and range for the client's requirements (Temperature Range: 0°C to 50°C, Humidity Range: 20% to 90%). Similar devices such as the DHT22, AHT20, or the AM2301B [^2] have higher specifications , however, the DHT11 uses a simple serial communication (SPI) rather than more elaborated protocols such as the I2C used by the alternatives. For the range, precision, and accuracy required in this application the DHT11 provides the best compromise. Connecting the DHT11 sensor to a computer requires a device that provides a Serial Port communication. A cheap and often used alternative for prototyping is the Arduino UNO microcontroller [^3]. "Arduino is an open-source electronics platform based on easy-to-use hardware and software"[^4]. In addition to the low cost of the Arduino (< 6 USD), this device is programable and expandable [^1]. Other alternatives include different versions of the original Arduino but their size and price make them a less adequate solution.

### Design statement
We will design and program a **low-cost sensing device composed of an Arduino, a DH11, and a USB cable**. This sensor will **measure humidity and temperature levels** for **48 hours** then the data will be interpreted and analyzed. This project is for our client who must determine and compare the weather conditions in their room and outside. The data will be interpreted and graphed using the software **PyCharm** and the language **Python**, taking **three weeks** to make. All of the findings will be displayed on an informational poster which will also include health consequences if found. The proposed solution will be evaluated according to **criteria A and B**.

[^1]: Industries, Adafruit. “DHT11 Basic Temperature-Humidity Sensor + Extras.” Adafruit Industries Blog RSS, https://www.adafruit.com/product/386. 
[^2]: Nelson, Carter. “Modern Replacements for DHT11 and dht22 Sensors.” Adafruit Learning System, https://learn.adafruit.com/modern-replacements-for-dht11-dht22-sensors/what-are-better-alternatives.   
[^3]:“How to Connect dht11 Sensor with Arduino Uno.” Arduino Project Hub, https://create.arduino.cc/projecthub/pibots555/how-to-connect-dht11-sensor-with-arduino-uno-f4d239.  
[^4]:Team, The Arduino. “What Is Arduino?: Arduino Documentation.” Arduino Documentation | Arduino Documentation, https://docs.arduino.cc/learn/starting-guide/whats-arduino.  
[^5]: GIPHY. “Rain Weather GIF by Hey Duggee - Find & Share on GIPHY.” Giphy.com, giphy.com/gifs/heyduggee-windy-rainy-badweather-YlGqroQd2gKIz6tPf0?utm_source=media-link&utm_medium=landing&utm_campaign=Media%20Links&utm_term=. Accessed 29 Nov. 2022.
[^6]: “Can Medications Make You More Sensitive to Sun and Heat?” Consumer Reports, www.consumerreports.org/drug-safety/can-medications-make-you-more-sensitive-to-sun-and-heat-a5178604785/.


## Success Criteria

1. The solution provides a visual representation of the Humidity and Temperature values inside a dormitory (Local) and outside the house (Remote) for a period of minimum 48 hours. 
1. ```[HL]``` The local variables will be measure using a set of 4 sensors around the dormitory.
2. The solution provides a mathematical modelling for the Humidity and Temperature levels for each Local and Remote locations. ```(SL: linear model)```, ```(HL: non-lineal model)```
3. The solution provides a comparative analysis for the Humidity and Temperature levels for each Local and Remote locations including mean, standad deviation, minimum, maximum, and median.
4. ```(SL)```The Local samples are stored in a csv file and ```(HL)``` posted to the remote server.
5. Create a prediction the subsequent 12 hours for both temperature and humidity.
6. A poster summarizing the visual representations, model and analysis is created and communicated.

# Criteria B: Design

## System Diagram **SL**
![](sysdim_sl.png)

**Fig.1** shows the system diagram for the proposed solution (**SL**). The indoor variables will be measured using an Arduino microprocessor and the sensor DHT11 conencted to the local computer (Laptop) located inside a room. The outdoor variables will be requested to the remote server using a GET request to the API of the server at ```192.168.6.147/readings```. The local values are stored in a CSV database locally.

## Flowchart 1 - Smoothing 
![Untitled Diagram drawio (2)](https://user-images.githubusercontent.com/105724334/207341359-f914fa35-6081-4541-a3ca-affdc40dccdd.png)


**Fig.2** shows the flow diagram of the code used to smooth the data collected. 

## Flowchart 2 - Saving data to CSV 
![Untitled Diagram drawio (4)](https://user-images.githubusercontent.com/105724334/207341390-18b2bf0a-1646-43fc-bb55-320008455a1b.png)


**Fig.3** shows the flow diagram of the program that appends and saves the data measured by the sensor to the csv. 

## Flowchart 3 - Gathering data
<img width="289" alt="Screen Shot 2022-12-14 at 10 18 44" src="https://user-images.githubusercontent.com/105724334/207481506-555d9682-7eb2-440a-b7f1-35679ff85f42.png">

**Fig.4** shows the flow diagram of the code used to connect the Arduino to the computer. Furthermore, this code also collects the data received from the DHT11 sensor and records it to the database. 

## Record of Tasks
| Task No | Planned Action                                                | Planned Outcome                                                                                                 | Time estimate | Target completion date | Criterion |
|---------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1 | Write the Problem Context  | Understand the requirements needed for the project  | 10 min | Nov 22 | A |
| 2 | Create Bill of Materials | Gather and gain possession of materials needed to collect data | 5 min  | Nov 22    | A  |
| 3 | Design Statement | Describe and articulate a clear outline of the project | 10 min | Nov 24 | A |
| 4 | Create data collection code | Be able to collect data from the DH11 sensor and view them on the computer | 40 min | Nov 30 | C |
| 5 | Create CSV | Humidity and temperature values will be saved on the database as they are collected | 20 min | Dec 01 | C | 
| 6 | Test #1 | Ensure connection and code are successful | 60 min | Dec 01 | B | 
| 7 | Develop MVP (Minimum Viable Product) | Test basic product before moving towards the final one | 120 min | Dec 02 | B |
| 8 | Start collecting data | Measure humidity and temperature levels | Dec 04 | C | 
| 9 | Create flowcharts | Clearly display the codes utilized in the making of the product | 60 min | Dec 04 | B |
| 10 | Research humidity and temperature information | Determine whether the student's room allign with the healthy humidity and temperature levels | 60 min | Dec 05 | D |
| 11 | Code the graphs for inside and outside data | Visualize the data collected | 80 min | Dec 09 | C |
| 12 | Create scientific poster | Concisely showcase the findings of the product | 200 min | Dec 11 | D |
| 13 | Video creation | Demonstrate and describe the product and how the success criteria has been met | 40 min | Dec 12 | D |
| 14 | Polish details on repository | Gather everything that must be added | 40 min | Dec 12 | B |


## Test Plan
| Software Test Type | Input | Process | Planned Output  |
|------|-------------|----------|---------|
| Functional: Unit Testing | Program that collects data from DHT11 sensor | 1. Connect DHT11 sensor to computer. 2. Run code. 3. Wait for output from DHT11 sensor. | Connection between sensor and computer has been established. |
| Functional: Performance Testing | Program to collect humidity and temperature levels from sensor every 5 minutes | 1. Run code. 2. Measure response time. | Data will be received and printed on the computer monitor at a 5 minute interval. |
| Functional: Unit Testing | Program that appends data collected to databse (temp_hum.csv) | 1. Run code. 2. Data is collected. 3. Data is printed and displayed into the database | Data will be collected and written on the database (temp_hum.csv) |
| Functional: Unit Testing | Program that graphs the collected values | 1. Run code. 2. Wait for graphs to be displayed. 3. Ensure the data showcased is concise (values are logical). | Confirm program has graphed data collected, linear model, standard deviation, mean, median, maximum, minimum, and prediction. |


## Minimum Viable Product
https://user-images.githubusercontent.com/105724334/206645578-aebaee53-4c5f-4f2a-93ec-a6dd298b4032.mov


The video demonstrates what happens when the code runs. 

<img width="1440" alt="Screen Shot 2022-12-13 at 23 02 39" src="https://user-images.githubusercontent.com/105724334/207356368-1bc58a15-dba6-489f-9ade-00d5f39a8670.png">
**Fig.5**
Displays how the temperature and humidity values were stored on the database (temp_hum.csv) on Python after the data was colected. 

An MVP prototype was created in order to essentially show how the product works at its simplest form. It runs on Python code once the computer has been successfully connected to the DHT11 sensor through the Arduino. The code allows the computer to collect the data that the sensor measures, and displays in the form of a graph. The data that is collected is also appended to the database (temp_hum.csv) as lists. For the MVP, the for loop values were set as (10, 1) meaning that the sensor measured the humidity and temperature every second 9 times. For the final product, meaning for when the data is collected for 48 hours, the values change as to gather data every 5 minutes (300 seconds) for 48 hours (576 times.)

For more details, please refer to the Python code below.
```.py
import serial
import time
import matplotlib.pyplot as plt

arduino = serial.Serial('/dev/cu.usbserial-1130', baudrate=9600, timeout=.1)
temp_list = []
humidity_list = []

plt.style.use = "ggplot"

def getTemp():
    data = ""
    while len(data)<1:
        data = arduino.readline()
    return data

for i in range(10):
    time.sleep(1)
    value = getTemp()
    msg = value.decode("utf-8")
    print(msg)
    if msg != "Hello\r\n":
        slicedata = msg.split(" ")
        print(slicedata)
        humidity = (slicedata[0].split(":")[1])
        humidity = float(humidity.replace("%",""))
        print(humidity)
        temp = (slicedata[1].split(":")[1])
        temp = float(temp.replace("C",""))
        print(temp)

        temp_list.append(temp)
        humidity_list.append(humidity)

import csv
with open('temp_hum.csv', 'a', newline="") as file:
    new_data = csv.writer(file)
    new_data.writerow(humidity_list)
    new_data.writerow(temp_list)

print(humidity_list)
print(temp_list)

fig = plt.figure(figsize=(10,4))
plt.subplot(1,2,1)
plt.plot(humidity_list, color="blue")
plt.title("Humidity")
plt.xlabel("Time")
plt.ylabel("Humidity (%)")

plt.subplot(1,2,2)
plt.plot(temp_list, color="red")
plt.title("Temperature")
plt.xlabel("Time")
plt.ylabel("Temperature (C)")

plt.show()
```

# Criteria C: Development

## Existing tools
| Software/development tools | Coding structure tools | Libraries    |
|----------------------------|------------------------|--------------|
| Python/Pycharm             | For loops, if statements | statistics |
| VNC viewer                 | API requests           | requests     |
|                            |                        | csv          |
|                            |                        | matplotlib   |
|                            |                        | numpy        |


## List of techniques used
| Technique |
|-----------|
| Retrieving data from a remote server with server API and requests library. |
| Connecting a DHT11 sensor with an Arduino to the computer. |
| For loops that run codes for extended periods of time under certain conditions. |
| Creating CSV files that save and write data from DHT11 sensors in separated lists (temperature and humidity). |
| Plotting the median, mean, maximum, minimum, standard deviation and a linear model using python. |
| Predicting temperature and humidity values based on the linear model. |
| Smoothing data on a graph. |

## Development
## Graphing Linear Model
```.py
import matplotlib.pyplot as plt
import numpy as np

#csv must have been imported by then
# plt.scatter(x,y)
# plt.title("Scatter Plot of the Data")
# plt.xlabel("x")
# plt.ylabel("y")
import matplotlib.pyplot as plt
import numpy as np
import requests as req
from matplotlib.gridspec import GridSpec

from scratches.unit_lib import smoothing

m, b = np.polyfit (x, y, 1)
print (f"The linear equation is y = {m:.2f}x + ({b:.2f})")
x_model = [0,2069]
y_model = []
for i in x_model:
    y_model.append (m * i + b)

# plt.style.use('_mpl-gallery')

plt.plot(x, y, linewidth=2.0, color='orange')
plt.plot(x_model, y_model, linewidth=2.0)
plt.title("humidity measurements in % for 48hours" )
plt.xlabel("time in minutes ")
plt.ylabel("humidity in %")


plt.show()
```


## Graphing data from the API Server
```.py
import requests
import matplotlib.pyplot as plt
import numpy as np


req = requests.get('http://192.168.6.142/readings')
data = req.json()
readings = data["readings"][0]

# get only temperature
T1 = []
T2 = []
for sample in readings:
    if sample["sensor_id"] == 8:
        T1.append(sample["value"])
    if sample["sensor_id"] == 9:
        T2.append(sample["value"])

# every 12 samples calculate the mean and std
number_samples_per_hour = 12
mean_per_hour = []
x = []
for t in range(0, len(T1), number_samples_per_hour):
    t_hour = T1[t:t+number_samples_per_hour]    # 12 values
    mean_per_hour.append(sum(t_hour)/len(t_hour))
    x.append(t)

# smoothing
x2 = []
mean_per_hour2 = []
for t in range(0, len(T2), number_samples_per_hour):
    t_hour = T2[t:t+number_samples_per_hour]    # 12 values
    mean_per_hour2.append(sum(t_hour)/len(t_hour))
    x2.append(t)

# difference as comparison
diff = []
for i in range(len(mean_per_hour)):
    d = mean_per_hour[i]-mean_per_hour2[i]
    diff.append(d)

fig=plt.figure(figsize=(9,6))
plt.subplot(3, 1, 1)
plt.title("Sensor 8 humidity")
plt.plot(x2, mean_per_hour2)
plt.subplot(3, 1, 2)
plt.title("Sensor 10 temperature")
plt.plot(x, mean_per_hour)
plt.subplot(3, 1, 3)
plt.plot(x, diff)
plt.show()
```

## Predcition for Humidity 
![Screen Shot 2022-12-13 at 21 04 53](https://user-images.githubusercontent.com/105724334/207484750-c51e763c-2091-4223-82b2-99181c4f4ae2.png)
![Screen Shot 2022-12-13 at 21 05 10](https://user-images.githubusercontent.com/105724334/207484754-f155b768-ab0e-4b8e-b5c9-aa8344a07f57.png)
Displays the prediction for humidity for the subsequent 12 hours. 

# Criteria D: Functionality
## Scientific Poster 
![1](https://user-images.githubusercontent.com/105724334/207482928-473d9d2a-ac25-4c0e-8f34-cc623d2fd203.png)

![2](https://user-images.githubusercontent.com/105724334/207482938-941cb8fd-c796-439b-aadb-dd8330e5763c.png)

**Fig. 6** displays the scientific poster that aims to summarize the product's findings. Humidity and temperature data is showcased clearly as well as scientific information to back up all claims. 

## Product Demonstration Video
A 7 min video that narrates the proposed solution and its functionality. 

### Works Cited
