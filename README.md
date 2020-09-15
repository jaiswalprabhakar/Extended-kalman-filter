# Extended-kalman-filter
Kalman Filter for linear systems and extend it to a nonlinear system such as a self-driving car. Apply the Kalman Filter on the data received by IMU, LIDAR and GPS and estimate the co-ordinates of a self-driving car and visualize its real trajectory versus the ground truth trajectory
Localization: 
         Robot localization is the process of determining where a mobile robot is located with respect to its environment. Localization is one of the most fundamental competencies required by an autonomous robot as the knowledge of the robot’s own location is an essential precursor to making decisions about future actions.
Kalman Filter
Kalman filtering is an algorithm that provides estimates of some unknown variables given the measurements observed over time. Kalman filters have been demonstrating its usefulness in various applications. Kalman filters have relatively simple form and require small computational power. 

Need of Kalman filter:
    Most of the modern systems are equipped with numerous sensors that provide estimation of hidden (unknown) variables based on the series of measurements. For example, the GPS receiver provides the location and velocity estimation, where location and velocity are the hidden variables and differential time of satellite's signals arrival are the measurements.
One of the biggest challenges of tracking and control system is to provide accurate and precise estimation of the hidden variables in presence of uncertainty. In the GPS receiver, the measurements uncertainty depends on many external factors such as thermal noise, atmospheric effects, slight changes in satellite's positions, receiver clock precision and many more.
Kalman Filter is one of the most important and common estimation algorithms. The Kalman Filter produces estimates of hidden variables based on inaccurate and uncertain measurements. As well, the Kalman Filter provides a prediction of the future system state, based on the past estimations.
 
The measurement is a random variable, described by the Probability Density Function (PDF).
The measurements mean is the Expected Value of the random variable.
The offset between the measurements mean and the true value is the measurements accuracy also known as bias or systematic measurement error.
The dispersion of the distribution is the measurement precision, also known as the measurement noise or random measurement error or measurement uncertainty.






ONE-DIMENSIONAL KALMAN FILTER:
   
•	Step 0: Initialization
the initialization performed only once, and it provides two parameters:
o	Initial System State ( x^1,0x^1,0 )
o	Initial State Uncertainty ( p1,0p1,0 )
The initialization is followed by prediction.
•	Step 1: Measurement
The measurement process shall provide two parameters:
o	Measured System State ( znzn )
o	Measurement Uncertainty ( rnrn )
•	Step 2: State Update
The state update process is responsible for system's current state estimation.
The state update process inputs are:
o	Measured Value ( z1,0z1,0 )
o	The Measurement Uncertainty ( rnrn )
o	Previous System State Estimate ( x^n,n−1x^n,n−1 )
o	Estimate Uncertainty ( pn,n−1pn,n−1 )
Based on the inputs, the state update process calculates the Kalman Gain and provides two outputs:
o	Current System State Estimate ( x^n,nx^n,n )
o	Current State Estimate Uncertainty ( pn,npn,n )
These parameters are the Kalman Filter outputs.
•	Step 3: Prediction
The prediction process extrapolates the current system state and the uncertainty of the current system state estimate to the next system state, based on the system's dynamic model.
At the first filter iteration the initialization outputs are treated as the Previous State Estimate and Uncertainty.
On the next filter iterations, the prediction outputs become the Previous State Estimate and Uncertainty.


Sensors Used: 
LIDAR: 
             LiDAR works in a similar way to Radar and Sonar yet uses light waves from a laser, instead of radio or sound waves. A LiDAR system calculates how long it takes for the light to hit an object or surface and reflect back to the scanner. The distance is then calculated using the velocity of light. These are known as ‘Time of Flight’ measurements.

LIDAR (Light Detection and Ranging) is an optical remote sensing system which can measure the distance of a target by illuminating it with light. LIDAR technology is being used in Robotics for the perception of the environment as well as object classification. The ability of LIDAR technology to provide 2D elevation maps of the terrain, high precision distance to the ground, and approach velocity can enable safe landing of robotic and manned vehicles with a high degree of precision.
Another method used to determine distance is the Phase-Shift Method. Instead of using a pulsed laser source, a continuous source is used where the power is modulated at a constant frequency. This means that the input can be looked at like a sine curve with time on the x-axis and laser power on the y-axis. Photodetectors can do more than just detect if there is light, it can also detect the power of light, thus a sine curve of the return signal can be formed. 
By comparing the phase difference, the difference in radians of the peaks of the waves, the distance to the object can be found with the following equation where d is distance, c is the speed of light, Δϕ is the phase difference, and f is the frequency at which the power was modulated.

With the use of iterative closest point algorithm, we can get x and y axis position data
which will be used in fusion with other sensor data like IMU and GPS.
 






MPU6050:
MPU6050 sensor module is an integrated 6-axis Motion tracking device.
It has a 3-axis Gyroscope, 3-axis Accelerometer, Digital Motion Processor and a Temperature sensor, all in a single IC.
It can accept inputs from other sensors like 3-axis magnetometer or pressure sensor using its Auxiliary I2C bus.
If external 3-axis magnetometer is connected, it can provide complete 9-axis Motion Fusion output.
A microcontroller can communicate with this module using I2C communication protocol. Various parameters can be found by reading values from addresses of certain registers using I2C communication.
Gyroscope and accelerometer reading along X, Y and Z axes are available in 2’s complement form. Temperature reading is also available in signed integer form.
Gyroscope readings are in degrees per second (dps) unit; Accelerometer readings are in g unit; and Temperature reading is in degrees Celsius.












Inside MPU 6050:




NEO-6M GPS Receiver Module:
•	Global Positioning System (GPS) makes use of signals sent by satellites in space and ground stations on Earth to accurately determine its position on Earth.
•	The NEO-6M GPS receiver module uses USART communication to communicate with microcontroller or PC terminal.
•	It receives information like latitude, longitude, altitude, UTC time, etc. from the satellites in the form of NMEA string. This string needs to be parsed to extract the information that we want to use.
•	We are going to display data (latitude, longitude, altitude and time) received by the GPS receiver module on the serial monitor of Arduino.
 




