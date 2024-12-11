# Criterion A: Planning

## Problem Definition:
### My client is Bread and Bakes, a local student-led business in the ISAK community that makes different kinds of bread which they later sell to the student population. Bread has an optimum humidity and temperature for proofing and baking. This is around 75% humidity levels as well as 22 - 25 degrees celsius for proofing. Due to the decrease of humidity and temperature in Karuizawa during fall, the owners of Bread and Bakes have hired our team to monitor the temperature of the apartment. By measuring the humidity and temperature levels in different houses, R3 and R2, they hope to find the best place to allow their bread to rise, consequently hoping for an increase in business. 

## Proposed Solution:
### Hardware: DHT11 Sensor: The DHT11 sensor is an affordable and reliable choice for measuring temperature and humidity, costing less than $5. It provides adequate precision for this project, with a temperature range of 0°C to 50°C and a humidity range of 20% to 90%, which align well with the requirements for monitoring bread-proofing conditions. Although other sensors, such as the DHT22 or AHT20, offer higher precision, their additional features are not essential for this application and would unnecessarily increase costs. The DHT11's use of Serial Peripheral Interface (SPI) for communication makes it simpler to integrate with other components compared to alternatives that rely on more complex protocols like I²C. Arduino Uno Microcontroller: The Arduino Uno serves as the intermediary for connecting the DHT11 sensor to a computer. Its low cost (approximately $6), programmability, and expandability make it an ideal choice. While alternatives such as advanced Arduino models exist, their higher cost and additional features are unnecessary for this project.
### Software: Python: Python is selected as the programming language due to its open-source nature, ease of use, and cross-platform compatibility. Its high-level programming structure simplifies tasks such as data processing and visualization, which are critical for this project. Unlike lower-level languages like C/C++, Python automates memory management and offers an extensive library ecosystem, enabling rapid development and scalability. Python also supports seamless integration with data visualization libraries, ensuring clear and effective communication of the results to the client.
### Data Visualization: To effectively present the findings to the client, a scientific poster will be created. This poster will include graphical representations of temperature and humidity trends in R2 and R3 over a 24-hour period. By comparing the data, the poster will highlight which location provides the most favorable environment for bread proofing. Clear visuals and concise analysis will ensure the results are actionable for the client.

# Criterion B: Solution Overview

## Record of Tasks:
# Record of Tasks

| **Date**       | **Task Description**                                                                                                         | **Planned Outcome**                                                                                                                                                                                                                           | **Time Estimate** | **Target Completion Date** | **Criterion** |
|----------------|-----------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|----------------------------|---------------|
| 2024-11-27    | Initial client meeting with Bread and Bakes to discuss the problem and project requirements.                                 | Understand the client’s needs: identify temperature and humidity monitoring requirements for optimal bread proofing.                                                                                                                         | 1 hour            | 2024-11-27                | A             |
| 2024-11-28    | Conducted research on sensor options (DHT11, DHT22, BMP280) and microcontrollers (Arduino UNO, ESP8266).                     | Select the best combination of hardware that meets the project’s budget, precision, and ease of implementation requirements.                                                                                                                 | 3 hours           | 2024-11-28                | A             |
| 2024-11-29    | Ordered DHT11 sensor, Arduino UNO, and accessories. Configured Arduino for basic serial communication.                       | Ensure that all required components are procured and ready for development and testing.                                                                                                                                                       | 2 hours           | 2024-11-29                | A             |
| 2024-11-30    | Tested DHT11 sensor for basic functionality and accuracy in recording temperature and humidity.                              | Verify that the DHT11 provides consistent and accurate readings under different conditions.                                                                                                                                                  | 2 hours           | 2024-11-30                | C             |
| 2024-12-01    | Discovered an issue: sensor readings showed occasional extreme spikes. Planned to implement a moving average filter.         | Smooth sensor data to eliminate noise and make trends more reliable for analysis.                                                                                                                                                            | 2 hours           | 2024-12-01                | C             |
| 2024-12-02    | Wrote and tested a Python function for moving average smoothing. Applied the filter to test data.                            | Smooth out sensor data, ensuring more reliable trends and reducing noise in the graphs.                                                                                                                                                      | 3 hours           | 2024-12-02                | C             |
| 2024-12-03    | Started logging sensor data to a CSV file with timestamps. Tested for continuous 24-hour data recording.                     | Create a robust data logging system to store temperature and humidity readings with timestamps.                                                                                                                                              | 3 hours           | 2024-12-03                | C             |
| 2024-12-04    | Encountered a failure: sensor disconnection caused program crashes. Implemented `try`-`except` error handling.               | Prevent program crashes during sensor errors, ensuring uninterrupted data logging.                                                                                                                                                           | 2 hours           | 2024-12-04                | C             |
| 2024-12-05    | Researched server integration and tested socket connections for server availability.                                         | Ensure reliable connection checks before attempting to upload data to the remote server.                                                                                                                                                     | 3 hours           | 2024-12-05                | C             |
| 2024-12-06    | Adjusted timeout settings in the socket library to fix intermittent connection test failures.                                | Improve reliability of server connection tests, reducing unnecessary errors during upload attempts.                                                                                                                                          | 1 hour            | 2024-12-06                | C             |
| 2024-12-07    | Developed script for uploading data to the server using JSON and authentication tokens.                                      | Successfully upload temperature and humidity data to the server for remote access by the client.                                                                                                                                             | 4 hours           | 2024-12-07                | C             |
| 2024-12-08    | Discovered an error: data upload script stopped working when authentication failed. Implemented fallback to local storage.   | Prevent data loss by saving locally when server upload fails, ensuring continuity and reliability of the system.                                                                                                                              | 3 hours           | 2024-12-08                | C             |
| 2024-12-09    | Collected 24-hour data from R2 and R3 locations. Created initial graphs of temperature and humidity trends.                  | Identify trends in temperature and humidity for comparison between the two locations.                                                                                                                                                        | 50 hours           | 2024-12-09                | C             |
| 2024-12-12   | Refined data visualization by applying moving average smoothing and limiting x-axis range to focus on key trends.            | Generate clear and concise graphs for presentation to the client.                                                                                                                                                                           | 2 hours           | 2024-12-10                | C             |
| 2024-12-12    | Finalized science poster, including methodology, graphs, and conclusions.                                                   | Prepare a professional and visually appealing science poster to explain findings and the solution to the client.                                                                                                                             | 4 hours           | 2024-12-11                | D             |
| 2024-12-13    | Filmed a 6–7 minute video demonstration showcasing the solution and the science poster.                                      | Demonstrate the project’s functionality, findings, and impact through a concise and engaging video.                                                                                                                                          | 10 Minutes          | 2024-12-12                | D             |
| 2024-12-13    | Presented the poster and video to the client. Gathered feedback and noted possible areas for future improvements.            | Ensure the client understands the solution and findings, making adjustments based on their feedback if required.                                                                                                                              | 2 hours           | 2024-12-13                | D             |
| 2024-12-14    | Conducted final debugging of the system to address minor inaccuracies in sensor data recording.                              | Ensure accuracy and reliability of data collection before delivering the final solution to the client.                                                                                                                                       | 2 hours           | 2024-12-14                | C             |
| 2024-12-15    | Delivered final report and solution package (code, CSV data, graphs) to the client.                                         | Provide the client with all necessary resources for implementing and understanding the solution for their bread-proofing process.                                                                                                            | 3 hours           | 2024-12-15                | D             |
| 2024-12-16    | Documented the entire development process for personal learning and portfolio purposes.                                      | Reflect on the project’s challenges and achievements, ensuring future development benefits from lessons learned.                                                                                                                             | 2 hours           | 2024-12-16                | D            |


## Test Plan:
# Test Plan

| **Test Case ID** | **Objective**                                                                                                                                                  | **Input**                                                                                          | **Expected Outcome**                                                                                                    | **Actual Outcome**                                                                                                     | **Pass/Fail** | **Date**       | **Notes**                                                                                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|---------------|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TC-001           | Verify sensor initialization and basic functionality.                                                                                                       | Power up Arduino and connect DHT11 sensor.                                                        | Sensor should initialize and start transmitting temperature and humidity data.                                         | Sensor successfully transmitted data without errors.                                                                   | Pass          | 2024-11-30    | Confirmed basic functionality of DHT11.                                                                                                                        |
| TC-002           | Test smoothness of the data after applying moving average filter.                                                                                           | Raw sensor data (with spikes).                                                                    | Output graph should show smooth, readable trends with reduced noise.                                                   | Graph trends were smooth with reduced noise.                                                                           | Pass          | 2024-12-02    | Filter function improved clarity of graphs.                                                                                                                     |
| TC-003           | Ensure proper data logging with timestamps to CSV file.                                                                                                    | 24-hour data collection session.                                                                  | CSV file should include all readings with accurate timestamps and sensor values.                                       | File was created with consistent timestamps and accurate sensor data.                                                  | Pass          | 2024-12-03    | Verified reliability of logging system.                                                                                                                          |
| TC-004           | Handle sensor disconnection.                                                                                                                    | Disconnect DHT11 sensor during operation.                                                         | Program should catch the error, log it, and continue running without crashing.                                         | Program logged the error and continued running.                                                                         | Pass          | 2024-12-04    | Error handling successfully implemented using `try`-`except`.                                                                                                     |
| TC-005           | Test server connection check using the socket library.                                                                                                     | Attempt to connect to the server with correct and incorrect IP addresses.                         | Program should verify connection before attempting data upload and notify the user of connection status.               | Correctly identified server availability and handled connection failures gracefully.                                    | Pass          | 2024-12-05    | Server availability checks worked as expected.                                                                                                                  |
| TC-006           | Ensure successful data upload to server with authentication.                                                                                               | Valid login credentials and valid sensor data payload.                                             | Data should upload to the server, and a confirmation message should be received.                                       | Data upload worked successfully with server confirmation.                                                              | Pass          | 2024-12-07    | Validated server-side integration and proper handling of JSON payloads.                                                                                           |
| TC-007           | Test fallback mechanism when server connection fails.                                                                                                      | Disconnect server during operation.                                                               | Data should be saved locally in a CSV file without program termination.                                                | Data was saved locally, and program notified user about local storage fallback.                                        | Pass          | 2024-12-08    | Fallback mechanism worked effectively to prevent data loss.                                                                                                       |
| TC-008           | Compare temperature and humidity trends between R2 and R3 locations.                                                                                       | 24-hour temperature and humidity data from both locations.                                        | Graphs should clearly show differences in trends and validate assumptions about the better bread-proofing environment. | Graphs highlighted differences in trends between locations as expected.                                                | Pass          | 2024-12-09    | Analysis provided useful insights for client recommendations.                                                                                                    |
| TC-009           | Validate accuracy of moving average implementation.                                                                                                        | Simulated data with known averages.                                                               | Filtered data should align closely with pre-calculated averages.                                                       | Filtered data matched expected results.                                                                                | Pass          | 2024-12-10    | Moving average implementation confirmed accurate.                                                                                                                 |
| TC-010           | Test system resilience during extended operation (24-hour continuous data logging).                                                                        | Run the system for 24 hours.                                                                      | Program should run without interruptions, recording all data accurately.                                               | System ran continuously without crashing, and data was accurately logged.                                              | Pass          | 2024-12-11    | Confirmed stability and reliability of the solution during prolonged operation.                                                                                   |
| TC-011           | Assess edge-case error handling for server upload failures (e.g., timeout or invalid credentials).                                                         | Simulate invalid login credentials or server timeout during upload attempts.                      | Program should notify the user and switch to local storage mode.                                                       | Properly handled failures and saved data locally.                                                                      | Pass          | 2024-12-12    | Additional testing of edge-case scenarios ensured robust error handling.                                                                                          |
| TC-012           | Evaluate data visualization clarity for the science poster.                                                                                                | Temperature and humidity data from sensors.                                                       | Graphs should clearly illustrate differences between locations and showcase trends effectively.                        | Graphs were clear and visually appealing for the poster presentation.                                                  | Pass          | 2024-12-13    | Visualization tools successfully communicated results for the client and audience.                                                                                |
| TC-013           | Test final system integration with all components (sensors, data logging, server upload, fallback).                                                       | 24-hour real-world test with all features enabled.                                                | System should function seamlessly, logging, and uploading data or saving locally as needed.                            | System performed as expected with no significant issues during integration test.                                        | Pass          | 2024-12-14    | Integration test confirmed end-to-end functionality.                                                                                                              |
| TC-014           | Verify accurate error messages and notifications for the user.                                                                                            | Disconnect sensor, simulate server failure, and introduce invalid data formats.                   | Program should provide clear and actionable error messages for each scenario.                                           | Error messages were clear and guided user appropriately.                                                               | Pass          | 2024-12-15    | Improved user experience by ensuring understandable feedback during errors.                                                                                        |
| TC-015           | Confirm user authentication robustness for server integration.                                                                                            | Use valid and invalid login credentials.                                                          | System should allow access only with valid credentials and reject invalid attempts.                                     | Authentication mechanism worked as intended.                                                                           | Pass          | 2024-12-16    | Authentication process was secure and reliable.                                                                                                                    |
| TC-016           | Validate performance of data logging and visualization scripts with large datasets.                                                                       | Simulate data collection for 72 hours and generate large CSV files.                               | Scripts should handle large datasets without crashing or significant delays in processing.                              | Successfully processed large datasets with minor delays in visualization.                                               | Pass          | 2024-12-17    | Prepared system for scalability and high-volume data collection.                                                                                                   |

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
