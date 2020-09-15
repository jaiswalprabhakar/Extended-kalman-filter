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






















