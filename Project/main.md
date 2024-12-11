# Criterion A: Planning

## Problem Definition:
### My client is Bread and Bakes, a local student-led business in the ISAK community that makes different kinds of bread which they later sell to the student population. Bread has an optimum humidity and temperature for proofing and baking. This is around 75% humidity levels as well as 22 - 25 degrees celsius for proofing. Due to the decrease of humidity and temperature in Karuizawa during fall, the owners of Bread and Bakes have hired our team to monitor the temperature of the apartment. By measuring the humidity and temperature levels in different houses, R3 and R2, they hope to find the best place to allow their bread to rise, consequently hoping for an increase in business. 

## Proposed Solution:
### Considering the client requirements an adequate solution includes a low cost sensing device for humidity and temperature and a custom data script that processes and analyzes the samples acquired. For a low cost sensing device an adequate alternative is the DHT11 sensor1 which is offered online for less than 5 USD and provides adequate precision and range for the client requirements (Temperature Range: 0°C to 50°C, Humidity Range: 20% to 90%). Similar devices such as the DHT22, AHT20 or the AM2301B 2 have higher specifications, however the DHT11 uses a simple serial communication (SPI) rather than more elaborated protocols such as the I2C used by the alternatives. For the range, precision and accuracy required in this application the DHT11 provides the best compromise. Connecting the DHT11 sensor to a computer requires a device that provides a Serial Port communication. A cheap and often used alternative for prototyping is the Arduino UNO microcontroller 3. "Arduino is an open-source electronics platform based on easy-to-use hardware and software"4. In addition to the low cost of the Arduino (< 6USD), this device is programmable and expandable1. I considered alternatives such as different versions of the original Arduino but their size and price make them a less adequate solution.
### Considering the budgetary constraints of the client and the hardware requirements, the software tool that I proposed for this solution is Python. Python's open-source nature and platform independence contribute to the long-term viability of the system. The use of Python simplifies potential future enhancements or modifications, allowing for seamless scalability without the need for extensive redevelopment 56. In comparison to the alternative C or C++, which share similar features, Python is a High level programming language (HLL) with high abstraction 7. For example, memory management is automatic in Python whereas it is the responsibility of the C/C++ developer to allocate and free up memory 7, this could result in faster applications but also memory problems. In addition, a HLL language will allow me and future developers to extend the solution or solve issues promptly.
### In order to represent our data visually to our client, we will be creating a poster that communicates our findings effectively. 

# Criterion B: Solution Overview

## Record of Tasks:
| **Date**       | **Task Description**                                          | **Planned Outcome**                                                                                         | **Time Estimate** | **Target Completion Date** | **Criterion**         |
|-----------------|--------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|-------------------|----------------------------|------------------------|
| 2024-11-25      | Initial meeting with Bread and Bakes to understand their needs. | Clearly define the problem: identify the need for monitoring proofing conditions in R2 and R3.                | 1 hour            | 2024-11-25                | Criterion A: Analysis |
| 2024-11-26      | Research and compare humidity and temperature sensors.         | Select a low-cost, suitable sensor (DHT11) for the project requirements.                                     | 2 hours           | 2024-11-26                | Criterion A: Analysis |
| 2024-11-27      | Design a prototype system for data collection using Arduino.   | Create a basic circuit setup with Arduino UNO and DHT11 for data collection.                                 | 3 hours           | 2024-11-28                | Criterion B: Development |
| 2024-11-29      | Develop and test Python script for real-time data logging.     | Create a functional Python program to log temperature, humidity, and pressure data from sensors.             | 4 hours           | 2024-11-30                | Criterion B: Development |
| 2024-11-30      | Deploy sensors in R2 and R3 to begin data collection.          | Record environmental data in both locations for a 24-hour period.                                            | 2 hours           | 2024-12-01                | Criterion C: Solution |
| 2024-12-02      | Analyze collected data and create visualizations.              | Generate graphs showing temperature, humidity, and pressure trends in R2 and R3.                             | 3 hours           | 2024-12-03                | Criterion C: Solution |
| 2024-12-03      | Begin drafting the science poster.                             | Complete initial sections of the poster: introduction, problem definition, and methodology.                  | 2 hours           | 2024-12-04                | Criterion C: Solution |
| 2024-12-04      | Feedback session with Bread and Bakes.                         | Present early results and poster outline to client for input and improvements.                               | 1 hour            | 2024-12-04                | Criterion C: Solution |
| 2024-12-05      | Refine Python script and update graphs with smoother outputs.  | Improved data accuracy and graph clarity to better represent the findings.                                   | 2 hours           | 2024-12-05                | Criterion C: Solution |
| 2024-12-06      | Finalize science poster and ensure print-readiness.            | Complete all sections of the poster, including results, conclusion, and recommendations.                     | 3 hours           | 2024-12-06                | Criterion C: Solution |
| 2024-12-07      | Record and edit a video demonstrating the project and poster.  | Produce a 6-7 minute video showcasing the solution, poster, and project workflow.                            | 4 hours           | 2024-12-08                | Criterion D: Evaluation |

## Test Plan:
| Test Case  | Objective                                  | Input                     | Expected Outcome                                | Estimated Time | Date Completed |
|------------|--------------------------------------------|---------------------------|-------------------------------------------------|----------------|----------------|
| 1          | Validate server login                      | Correct username/password | Access token is received                        | 30 minutes     | Dec 1st        |
| 2          | Verify sensor data collection from Arduino | Sensor data line          | Logged data matches the input                   | 1 hour         | Dec 1st        |
| 3          | Ensure data upload to the server           | Sensor ID and value       | Data upload response confirms success           | 30 minutes     | Dec 2nd        |
| 4          | Handle server disconnection                | Server is unavailable     | Data is saved locally, failure count increments | 3 days         | Dec 5th        |

## Systems Diagram:
<img width="961" alt="Screenshot 2024-12-09 at 9 31 53 AM" src="https://github.com/user-attachments/assets/8c81dac5-635a-41ad-8714-aa45c741b063">

## Flow Diagrams:
### Server Log In: 
<img width="421" alt="Screenshot 2024-12-09 at 0 53 50 AM" src="https://github.com/user-attachments/assets/ed507c23-655a-4018-a384-249b4234f5b0">

### Sensor Data Processing:
<img width="590" alt="Screenshot 2024-12-09 at 1 01 45 AM" src="https://github.com/user-attachments/assets/f20b310e-5a1c-4c9f-a1cf-f234c6b18c5d">

### Data Upload to Server: 
<img width="584" alt="Screenshot 2024-12-09 at 1 04 23 AM" src="https://github.com/user-attachments/assets/b72fa5f5-6101-4d1b-9d9f-b57df1041309">

## Data Storage Examples:

#### CSV File Format:
```.py
Timestamp, DHT11 Temp (°C), DHT11 Humidity (%), BMP280 Temp (°C), BMP280 Pressure (hPa)
2024-12-08 15:23:45, 22.34, 45.67, 21.78, 1013.25
```
#### JSON Example for Server Upload::
{
  "sensor_id": 245,
  "value": "22.34"
}

## Development Process:

### Purpose:
The project collects environmental data (temperature, humidity, and pressure) using sensors, logs it locally, and uploads it to a server for analysis.

### Development Steps:

#### Setup and Testing:
Configured Arduino and Python serial communication.
Set up server authentication using POST requests.
#### Data Logging:
Captured data from the DHT11 and BMP280 sensors.
Logged data in a CSV file with timestamps.
#### Server Communication:
Implemented API calls for data upload.
Handled server disconnections gracefully by saving data locally.
#### Error Handling:
Added checks for server availability.
Logged failures and provided actionable feedback.

# Criterion C: Development 

## List of Techniques:
### 1. Data Logging to CSV
### 2. Error Handling for Sensor Readings
### 3. Data Smoothing Using a Moving Average
### 4. Inclusion of Time Function

## Why these features?:
### 1. Data Logging to CSV Files
#### Problem/Purpose: The client needs a record of environmental conditions (temperature, humidity, and pressure) over time to analyze trends and compare proofing locations. Therefore I decided that storing data in a CSV file ensures easy access, reusability, and compatability for further analysis. Another benefit I noticed was that this feature also serves as the final fail safe in the event of a failed server upload after 3 attempts, where the data from the file can be used for analysis instead of the data from the server. Overall, this feature just serves as a guarantee that the code only ever needs to run once to collect all data, regrdless of network conditions.
#### Code:
```.py
with open("Collected _dat2.csv", "w") as data_file:
    #header
    data_file.write("Timestamp, DHT11 Temp (°C), DHT11 Humidity (%), BMP280 Temp (°C), BMP280 Pressure (hPa)\n")
    #collecting data and printing for monitoring
    print("Starting data collection for 24 hours...")

    while datetime.now() < end_time:
        if arduino_serial.in_waiting > 0:
            line = arduino_serial.readline().decode('utf-8').strip()
            print("Received:", line)

        if "DHT11" in line and "BMP280" in line:
            parts = line.split(",")
            dht_temp = float(parts[0].split(":")[1].strip()[:-2])
            dht_hum = float(parts[1].split(":")[1].strip()[:-1])
            bmp_temp = float(parts[2].split(":")[1].strip()[:-2])
            bmp_pres = float(parts[3].split(":")[1].strip()[:-3])

            time_stamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
            log_data(data_file, dht_temp, dht_hum, bmp_temp, bmp_pres)
            print(f"Logged: {time_stamp}, {dht_temp} °C, {dht_hum} %, {bmp_temp} °C, {bmp_pres} hPa")
        else:
            print("Where is my data?")
```
#### Explanation: 
##### data_file.write(): This line initialises the data file and prints the header so the data in the file can be more easily interpeted.
##### Data Parsing and Logging: The split() method breaks the line into individual components, each sensor's value is extracted and converted to a floating point number (e.g., dht_temp for DHT11 temperature).
##### Main Data Collection Loop: Inside the loop, the program checks if data is available from the Arduino serial port (arduino_serial). If data is available, it reads one line, decodes it from bytes to a string, and strips extra whitespace.

### 2. Error Handling for Sensor Readings
#### Problem/Purpose: Sensor errors or communication failures would cause my program to crash and stop recording data, which would affect the reliability of my solution. To prevent this, I implemented error handling to ensure the system remains functional without introducing errors or requiring me to manually restart the program. Restarting would introduce inaccuracies in the data and create issues like inconsistencies in the length of data and disparities between readings.
#### Code:
```.py
def check_connection(host=server_ip, port=80, timeout=3):
    try:
        socket.setdefaulttimeout(timeout)
        socket.create_connection((host, port))
        return True
    except OSError:
        return False
import socket

if check_connection():
  try:
  r = requests.post(f'http://{server_ip}/login', json=user)
  access_token = r.json()['access_token']
  auth = {"Authorization": f"Bearer {access_token}"}
  data = {'sensor_id': dht_temp_id, 'value': f'{dht_temp:2f}'}
  r = requests.post(f'http://{server_ip}/reading/new', json=data, headers=auth)
  print(r.json())
else:
  print("No server connection saving locally")
  time.sleep(60)
```
#### Explanation:
##### Socket: By using the socket library, I allowed my program to directly test the connection to the server before executing the upload code, ensuring a successful upload and preventing an error message.  
##### Try-Except: I used a try-except block as a second layer of this fail-safe. If a connection exists but the program “tries” to upload and fails, instead of crashing, it simply moves to the except function and continues running smoothly.
##### Authenticated Upload: Sends a POST request to the server to authenticate and obtain an access_token and constructs an authorization header and formats the sensor data (dht_temp) into a JSON payload.

### 3. Data Smoothing Using a Moving Average
#### Problem/Purpose: Raw sensor data often contains noise, such as extreme highs and lows, which makes it challenging for me to identify clear trends. To address this, I applied a moving average filter to smooth the data. This helped me create graphs and analysis that are more presentable and meaningful for the client, while also reducing the prominence of extreme variations in the data.
#### Code:
```.py
def moving_average(windowSize:int, x:list)->list:
    x_smooth = []
    for i in range(0, len(x)-windowSize):
        x_section = x[i:i+windowSize]
        x_average = sum(x_section)/windowSize
        x_smooth.append(x_average)
    return x_smooth

#Dht
box2 = fig.add_subplot(grid[0:3,1:3])
temp_smooth = moving_average(windowSize=10, x=y[211])
plt.plot(temp_smooth, color='salmon', label='DHT temp')
plt.ylabel('Temperatures (C)')
```
#### Explanation:
##### Function Definition: Defines a reusable function moving_average that accepts windowSize, The number of data points to average in each step and x, A list of raw sensor readings.
##### Moving Window Logic: Loops through the data, creating "windows" of size windowSize.
##### Integration with the Graph: Applies the moving_average function to temperature data (y[211]) and plots the smoothed temperature readings using Matplotlib with a specific color and label.

### 4. Inclusion of Time Function
#### Problem/Purpose: I Included this section because due to the recording session being 24 hours long, I did not want to time it myself and manually end the program. Due to my busy lifestyle it was more feesable for me to find a way to end the program automatically; this is where the datetime and timedelta functions come into play. 
```.py
end_time = datetime.now() + timedelta(minutes=623)

    while datetime.now() < end_time:
        if arduino_serial.in_waiting > 0:
            line = arduino_serial.readline().decode('utf-8').strip()
            print("Received:", line)
```
#### Explanation:
##### End Time Calculation: Uses Python's datetime and timedelta modules to calculate the end time for data collection.
##### While Loop for Time Management: Continuously checks the current time against the predefined end_time and ensures the loop runs only within the specified time frame, maintaining control over data collection duration.

## Sources: 
### DHT:
##### https://www.circuitbasics.com/how-to-set-up-the-dht11-humidity-sensor-on-an-arduino/
### BME:
##### https://iotdesignpro.com/projects/interfacing-bmp280-with-arduino-to-read-pressure-temperature-and-altitude
### Socket:
##### https://docs.python.org/3/library/socket.html
### DATE TIME:
##### https://docs.python.org/3/library/datetime.html
### PY serial:
##### https://pyserial.readthedocs.io/en/latest/
### Error Handling:
##### https://docs.python.org/3/tutorial/errors.html
### Arduino - Python Serial
##### https://projecthub.arduino.cc/ansh2919/serial-communication-between-python-and-arduino-663756
### Extra:
##### Past programs done throughout unit 2

# Criterion D: Functionality
## FULL Readings:
### Data from R2:
![Figure_1](https://github.com/user-attachments/assets/e149d9ec-a808-4d0b-90e9-98f9e6b011c6)
### Data from R3:
![Figure_2](https://github.com/user-attachments/assets/8696ad43-2ddc-4894-a76d-963b9094f2a1)

## Scientific poster showing findings:
![Beige and White Contemporary Editorial Landscape University Research Poster](https://github.com/user-attachments/assets/24bccb03-e4a8-4890-8832-fbbbdad680d6)
## Video oveview of Project:
Link to file in Google Drive: https://drive.google.com/drive/my-drive?dmr=1&ec=wgc-drive-globalnav-goto
