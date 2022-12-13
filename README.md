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

‌

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
## Minimum Viable Product
https://user-images.githubusercontent.com/105724334/206645578-aebaee53-4c5f-4f2a-93ec-a6dd298b4032.mov
**Fig.2**  


# Criteria C: Development

## List of techniques used

## Development


# Criteria D: Functionality

A 7 min video demonstrating the proposed solution with narration

### Works Cited
