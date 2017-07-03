## Description ##

This project allows remote control of a Roomba cleaning robot for moving, beeping, receiving messages and recording videos (current goals). 

A Meteor app runs locally on a computer, connects to an online Mongo database, and sends commands to a Raspberry Pi to control the robot.

## Instruction ##

Once you set up the hardware(see IPARobotv2(hardware).md)), do:

- Set up Meteor
- Set up Raspberry Pi

## Requirements ##

- Install [Meteor](https://www.meteor.com/install)
- Set up a database with MongoDB (free testing database at <https://mlab.com/welcome/>). First create an account and then create a new user.

## Installation ##

##### Meteor #####

1. Clone the repository and cd into the robo_server directory on your own computer:


		git clone https://github.com/cromaLab/IPA_Robot.git
		cd [the place you stored the repository locally]/IPA_Robot/robot_control_meteor/robo_server


2. Set url for your remote mongoDB and run Meteor app:

		MONGO_URL="mongodb://[dbUSERNAME]:[dbPASSWORD]@[dbURL]" meteor
		
3. Open a web browser and navigate to ```http://localhost:3000/status```

##### Raspberry Pi #####

1. - Connect the Raspberry Pi to a monitor(make sure you also charge the Pi), plug in the USB of mouse&keyboard to the Pi. Open the terminal icon on Desktop.

   - Clone the repository:

			git clone https://github.com/cromaLab/IPA_Robot.git


   - Get the [raspberry_pi_ip] by running ```hostname -I```

2. Connect the Raspberry Pi with the roomba by communication cable.

3. Login to the Raspberry Pi on your own terminal romotely (default password is ```raspberry```):

        ssh pi@[raspberry_pi_ip]

4. Run the python receiver script on your terminal:

		python IPA_Robot/robot_control_meteor/python_receiver
		


#### Misc/Tips ####
- If you receive a ```connection time out``` error, it is likely that you have entered a wrong Raspberry IP

- To run the python script on startup of the raspberry pi, add ```python IPA_Robot/robot_control_meteor/python_receiver``` to your ~/.bashrc file
