# grab_safety_challenge

Enter the Path Name of the folder containing the feature files in the file_path 
Download the model ("finalized_model.sav") and save it the same folder
Training AUC is 0.7012 using hyperparameter Optimization


Feature Engineering

The idea of Rash driving can be classified as combination of Speed and Movement, where Speed is defined as speed along the direction of the car and Movement is defined as angular change in the GPS Bearing.
High speed alone may not be enough for Rash Driving and similarly angular change also will not define rash driving. A combination of both Speed and Movement is needed to classify Rash driving.

The idea is to Combine ZIG-ZAG movements with High Speed and other indicators of Rash Movement.
	
	Movement : Change in the GPS Bearing across time will depict the the angular change per second in the direction of car.
	
	Sign: If change in movement is along the different direction (clockwise and then anticlockwise or anticlockwise and then clockwise) in two consecutive seconds, it is non-zero else it is zero.
	
	Abs_Movement: Absolute Movement per second irrespective of direction(clockwise ot anticlockwise)
	
	Total Movement: Sum of Movement per second over the duration of the booking
	
	Duration: Analysis showed that Higher proportion of bookings with higher duration are classified as Rash.
	
	Acceleration: Change in Speed per second
	
	gyro_xyz: Total Gyro Movement as square root of the sum of squares of gyro movment in x,y and z direction. This tells that the ride is bumpy
	
	Rolling Movement: Rolling Average of Movement
	
	Rash_Movement: If the Rolling Average of Movement is above Threshold cutoff for permissible movement, it is classified as Rash Movement else zero.
	
	Total_Movement_by_duration: Average Movement for the booking. It is calculates as Total Movement over Total Duration of the Booking.
	
	Rolling_Speed : Rolling Average of Movement
	
	Average Speed: Average Speed of the Booking
	
	Median Speed: Median Speed of the Booking
	
	Rash_ Speed: If the Rolling Speed is above a certain threshold it is classified as 1 or else 0
	
	acc_movement: If the Acceleration is above a certain threshold it is classified as 1 or else 0
	
	gyro_movement: If the gyro_xyz is above a certain threshold it is classified as 1 or else 0
	
	sign_s: Instance where both Rash Speed and Sudden Change(Sign) in angular direction are there
	
	a_m: Instance where both acc_movement and gyro_movement are there
	
	a_s: Instance where both acc_movement and Rash Speed are there
	
	sign_m: Instance where both Rash Speed and Sudden Change(Sign) in angular direction are there
	
	a_m_s: Instance where both Rash Speed , Acc_movement and gyro_movement are there
	
	sign_a_m_s: Instance where both Sudden Change(Sign) in angular direction, Rash Speed , Acc_movement and gyro_movement are there
