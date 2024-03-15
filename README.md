# The usage of RPLidar A2M12 with Raspberry Pi
I ran the RPLidar A2M12 using Raspberry Pi 4 Model B. I did this on the Debian Bullseye operating system of Raspberry Pi. While some RPLidar projects use systems like ROS, the reason I used simple grabber is because ROS is not compatible with Debian Bullseye. I connected the RPLidar to the Raspberry Pi via USB.

# SDK DOWNLOAD
Download the SDK directly from the GitHub repository:
wget https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip

Extract the zip file:
unzip master.zip

Navigate to the downloaded directory:
cd rplidar_sdk-master/sdk

Compile the SDK:
make

*This command will trigger the execution of the Makefile.txt. If there had been a CMakeLists.txt file instead of this .txt file, you would need to first enter "cmake ." command. After entering the "cmake" command, enter the "make" command.

*After entering the make command, an output file will be generated.

Navigate to the directory where the executable file is located:
cd rplidar_sdk/output/Linux/Release/

Find the executable files:
find . -type f -executable

*This command helps you find out which executable files exist. When you enter this command, it should find three executable files named simple_grabber, ultra_simple, and custom_baudrate.

# RUNNING RPLIDAR
To find out which port RPLidar is connected to, enter this command:
ls -l /dev|grep ttyUSB

Run the executable files:
./simple_grabber --channel --serial /dev/ttyUSB0 256000

*You can use ultra_simple instead of simple_grabber here if you want, but I recommend using simple_grabber as it is more functional and useful than ultra_simple.

*If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.

*This command only ensures that RPLidar is running and the received data is displayed on the terminal. If you want to save the received data to a .txt file, follow these steps.

To create a file named veriler.txt, enter this command in the terminal:
touch veriler.txt

To run RPLidar and save the received data to the veriler.txt file, enter this command:
./simple_grabber --channel --serial /dev/ttyUSB0 256000 > veriler.txt 2>&1

*If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.

Then simply type y in the terminal. This is a fine detail to ensure that the received data is saved to the veriler.txt file. To stop the rotation of the RPlidar, simply press the "enter" key without typing anything.
