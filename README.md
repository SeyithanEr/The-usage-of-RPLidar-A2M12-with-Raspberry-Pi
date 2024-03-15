# The usage of RPLidar A2M12 with Raspberry Pi
I ran the RPLidar A2M12 using Raspberry Pi 4 Model B. I did this on the Debian Bullseye operating system of Raspberry Pi. While some RPLidar projects use systems like ROS, the reason I used simple grabber is because ROS is not compatible with Debian Bullseye. I connected the RPLidar to the Raspberry Pi via USB. You need to type these commands into the terminal of your Raspberry Pi.

# SDK DOWNLOAD
## Download the SDK directly from the GitHub repository:

wget https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip


## Extract the zip file:

unzip master.zip


## Navigate to the downloaded directory:

cd rplidar_sdk-master/sdk


## Compile the SDK:

make


*This command will trigger the execution of the Makefile.txt. If there had been a CMakeLists.txt file instead of this .txt file, you would need to first enter "cmake ." command. After entering the "cmake" command, enter the "make" command.


*After entering the make command, an output file will be generated.


## Navigate to the directory where the executable file is located:

cd rplidar_sdk/output/Linux/Release/


## Find the executable files:

find . -type f -executable


*This command helps you find out which executable files exist. When you enter this command, it should find three executable files named simple_grabber, ultra_simple, and custom_baudrate.

# RUNNING RPLIDAR
## To find out which port RPLidar is connected to, enter this command:

ls -l /dev|grep ttyUSB


## Run the executable files:

./simple_grabber --channel --serial /dev/ttyUSB0 256000


*You can use ultra_simple instead of simple_grabber here if you want, but I recommend using simple_grabber as it is more functional and useful than ultra_simple.


*If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.


*This command only ensures that RPLidar is running and the received data is displayed on the terminal. If you want to save the received data to a .txt file, follow these steps.


## To create a file named data.txt, enter this command in the terminal:

touch data.txt


## To run RPLidar and save the received data to the data.txt file, enter this command:

./simple_grabber --channel --serial /dev/ttyUSB0 256000 > veriler.txt 2>&1


*If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.


Then simply type y in the terminal. This is a fine detail to ensure that the received data is saved to the data.txt file. To stop the rotation of the RPlidar, simply press the "enter" key without typing anything.    

## Parts

The tools I used for the project:
| Name | Link |
| --- | ---|
| RPLIDAR | https://tls.tc/auHiB |
| RASPBERRY Pİ | https://tls.tc/So5A1 |



{\rtf1\ansi\deff0\nouicompat{\fonttbl{\f0\fnil\fcharset0 Calibri;}{\f1\fnil\fcharset162 Calibri;}{\f2\fnil\fcharset238 Calibri;}{\f3\fnil\fcharset0 Courier New;}{\f4\fnil\fcharset0 Bahnschrift Light;}{\f5\fnil\fcharset162 Courier New;}}
{\colortbl ;\red0\green0\blue255;\red0\green0\blue0;}
{\*\generator Riched20 10.0.19041}\viewkind4\uc1 
\pard\sa200\sl276\slmult1\f0\fs22\lang31\par
\ul\b\f1\fs32\lang1055 SDK \f2\u304?\f1 ND\f2\u304?\f1 RME\ulnone\b0\f0\fs22\lang31\par
\b\i\fs24 SDK'y\f2\u305? GitHub deposundan do\u287?rudan indirin:\b0\i0\f0\fs22\par
\f3 wget {{\field{\*\fldinst{HYPERLINK https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip }}{\fldrslt{https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip\ul0\cf0}}}}\f4\fs22\par
\f0\par
\b\i\fs24 Zip dosyas\f2\u305?n\u305? \f0\lang1033\'e7\f2\u305?kart\u305?n:\b0\i0\f0\fs22\lang31\par
\f3 unzip master.zip\f0\par
\par
\b\i\f2\fs24\lang1055\u304?\f1 ndirdi\f2\u287?\f1 imiz dosyay\f2\u305?\f1  a\f0\lang1033\'e7\f2\lang1055\u305?\f1 n:\b0\i0\f0\fs22\lang31\par
\f3 cd rplidar_sdk-master/sdk\f0\par
\par
\b\i\fs24 Derlemeyi yap\f2\u305?n:\b0\i0\f0\fs22\par
\f3 make\f0\par
\par
\b\i\f1\lang1055 *Bu kod Makefile.txt dosyas\f2\u305?\f1 n\f2\u305?\f1 n \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 mas\f2\u305?\f1 n\f2\u305?\f1  sa\f2\u287?\f1 layacakt\f2\u305?\f1 r. E\f2\u287?\f1 er ki bu .txt dosyas\f2\u305?\f1  yerine CMakeList.txt dosyas\f2\u305?\f1  bulunsayd\f2\u305?\f1 , ilk \f0\lang1033\'f6\f1\lang1055 nce "cmake ." komutunu girmeniz gerekiyor. "cmake" komutunu girdikten sonra "make" komutunu girin.\par
\par
*make komutunu girdikten sonra output isimli bir dosya olu\f2\'ba\f1 acakt\f2\u305?\f1 r.\b0\i0\f0\lang31\par
\par
\b\i\f1\fs24\lang1055 Y\f0\lang31\'fcr\'fct\'fclebilir dosyan\f2\u305?n bulundu\u287?u dizine gidin\f1\lang1055 :\b0\i0\f0\fs22\lang31\par
\f3 cd rplidar_sdk/output/Linux/Release/\f0\par
\par
\b\i\f1\fs24\lang1055 Y\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 t\f0\lang1033\'fc\f1\lang1055 lebilir dosyalar\f2\u305?\f1  bulun:\b0\i0\f0\fs22\lang31\par
\f3 find . -type f -executable\f0\par
\par
\b\i\f1\lang1055 *Bu komut y\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 t\f0\lang1033\'fc\f1\lang1055 lebilir dosyalar\f2\u305?\f1 n hangilerini oldu\f2\u287?\f1 unu bulman\f2\u305?\f1 z\f2\u305?\f1  sa\f2\u287?\f1 lar. Bu komutu girdi\f2\u287?\f1 inizde simple_grabber , ultra_simple ve custom_baudrate adl\f2\u305?\f1  \f0\lang1033\'fc\'e7\f1\lang1055  tane y\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 t\f0\lang1033\'fc\f1\lang1055 lebilir dosya bulmas\f2\u305?\f1  gerekir. \b0\i0\f0\lang31\par
\par
\cf2\ul\b\f1\fs32\lang1055 RPL\f2\u304?\f1 DAR'I \f0\lang1033\'c7\f1\lang1055 ALI\f2\'aa\f1 TIRMA\cf0\ulnone\b0\fs22\par
\b\i\fs24 RPLidar'\f2\u305?\f1 n hangi port'a ba\f2\u287?\f1 l\f2\u305?\f1  oldu\f2\u287?\f1 unu bulmam\f2\u305?\f1 z i\f0\lang1033\'e7\f1\lang1055 in bu komutu girin:\b0\i0\fs22\par
\f5 ls -l /dev|grep ttyUSB\f1\par
\par
\b\i\fs24 Y\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 t\f0\lang1033\'fc\f1\lang1055 lebilir dosyalar\f2\u305?\f1  \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 t\f2\u305?\f1 r\f2\u305?\f1 n:\b0\i0\fs22\par
\f5 ./simple_grabber --channel --serial /dev/ttyUSB0 256000\f1\par
\par
\b\i *Hangi y\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 t\f0\lang1033\'fc\f1\lang1055 lebilir dosyay\f2\u305?\f1  kullanmak istiyorsan\f2\u305?\f1 z burada simple_grabber yerine ultra_simple'yi de kullanabilirsiniz. Fakat ultra_simple, simple_grabber'den daha kullan\f2\u305?\'ba\f1 s\f2\u305?\f1 z ve i\f2\'ba\f1 lev y\f0\lang1033\'f6\f1\lang1055 n\f0\lang1033\'fc\f1\lang1055 nden daha basit oldu\f2\u287?\f1 undan dolay\f2\u305?\f1  simple_grabber'i kullanman\f2\u305?\f1 z\f2\u305?\f1  tavsiye ederim. \b0\i0\par
\par
\b\i *E\f2\u287?\f1 erki elinizde RPLidar A2M12 varsa bu komut \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 acakt\f2\u305?\f1 r ama elinizde ba\f2\'ba\f1 ka bir RPLidar s\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 m\f0\lang1033\'fc\f1\lang1055  varsa Lidar'\f2\u305?\f1 n\f2\u305?\f1 z\f2\u305?\f1 n hangi baund'da \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 t\f2\u305?\u287?\u305?\f1 na g\f0\lang1033\'f6\f1\lang1055 re "256000" say\f2\u305?\f1 s\f2\u305?\f1 n\f2\u305?\f1  de\f2\u287?\f1 istirin.\par
\b0\i0\par
\b\i *Bu komut sadece RPLidar'\f2\u305?\f1 n \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 mas\f2\u305?\f1 n\f2\u305?\f1  ve al\f2\u305?\f1 nan verilerin terminalde g\f0\lang1033\'f6\f1\lang1055 sterilmesini sa\f2\u287?\f1 lar. Al\f2\u305?\f1 nan verilerin bir .txt dosyas\f2\u305?\f1 na kaydedilmesini istiyosan\f2\u305?\f1 z \f2\'ba\f1 u ad\f2\u305?\f1 mlar\f2\u305?\f1  uygulay\f2\u305?\f1 n.\b0\i0\par
\par
\par
\b\i\fs24 veriler.txt ad\f2\u305?nda bir dosya olu\'baturmak i\f0\lang1033\'e7in terminalde \f1\lang1055 bu komutu girin:\b0\i0\fs22\par
\f5 touch veriler.txt\f1\par
\par
\b\i\fs24 RPLidar'\f2\u305?\f1 n \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 mas\f2\u305?\f1  ve al\f2\u305?\f1 nan verilerin veriler.txt dosyas\f2\u305?\f1 na kaydelmesi i\f0\lang1033\'e7\f1\lang1055 in komutu girin:\b0\i0\fs22\par
\f5 ./simple_grabber --channel --serial /dev/ttyUSB0 256000 > veriler.txt 2>&1\par
\f1\par
\b\i *E\f2\u287?\f1 erki elinizde RPLidar A2M12 varsa bu komut \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 acakt\f2\u305?\f1 r ama elinizde ba\f2\'ba\f1 ka bir RPLidar s\f0\lang1033\'fc\f1\lang1055 r\f0\lang1033\'fc\f1\lang1055 m\f0\lang1033\'fc\f1\lang1055  varsa Lidar'\f2\u305?\f1 n\f2\u305?\f1 z\f2\u305?\f1 n hangi baund'da \f0\lang1033\'e7\f1\lang1055 al\f2\u305?\'ba\f1 t\f2\u305?\u287?\u305?\f1 na g\f0\lang1033\'f6\f1\lang1055 re "256000" say\f2\u305?\f1 s\f2\u305?\f1 n\f2\u305?\f1  de\f2\u287?\f1 istirin.\b0\i0\par
\par
\b\i\fs24 Sonras\f2\u305?\f1 nda terminale sadece y yaz\f2\u305?\f1 n. Bu, al\f2\u305?\f1 nan verilerin veriler.txt adl\f2\u305?\f1  dosyaya kaydedilmesi i\f0\lang1033\'e7\f1\lang1055 in en ince detayd\f2\u305?\f1 r. ve RPlidar\f2\u305?\f1 n d\f0\lang1033\'f6\f1\lang1055 nmesini durdurmak i\f0\lang1033\'e7\f1\lang1055 in ise hi\f0\lang1033\'e7\f1\lang1055 bir \f2\'ba\f1 ey yazmadan "enter" tu\f2\'ba\f1 una bas\f2\u305?\f1 n.\b0\i0\fs22\par
\f0\lang31\par
\b\fs32\par
\par
\par
SDK DOWNLOAD\b0\fs22\par
\b\i\fs24 Download the SDK directly from the GitHub repository:\b0\i0\fs22\par
\f3 wget {{\field{\*\fldinst{HYPERLINK https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip }}{\fldrslt{https://github.com/Slamtec/rplidar_sdk/archive/refs/heads/master.zip\ul0\cf0}}}}\f3\fs22\par
\f0\par
\b\i\fs24 Extract the zip file:\b0\i0\fs22\par
\f3 unzip master.zip\par
\f0\par
\b\i\fs24 Navigate to the downloaded directory:\b0\i0\fs22\par
\f3 cd rplidar_sdk-master/sdk\f0\par
\par
\b\i\fs24 Compile the SDK:\b0\i0\fs22\par
\f3 make\f0\par
\par
\b\i *This command will trigger the execution of the Makefile.txt. If there had been a CMakeLists.txt file instead of this .txt file, you would need to first enter "cmake ." command. After entering the "cmake" command, enter the "make" command.\b0\i0\par
\par
\b\i *After entering the make command, an output file will be generated.\par
\b0\i0\par
\b\i\fs24 Navigate to the directory where the executable file is located:\b0\i0\fs22\par
\f3 cd rplidar_sdk/output/Linux/Release/\par
\f0\par
\b\i\fs24 Find the executable files:\b0\i0\fs22\par
\f3 find . -type f -executable\f0\par
\par
\b\i *This command helps you find out which executable files exist. When you enter this command, it should find three executable files named simple_grabber, ultra_simple, and custom_baudrate.\b0\i0\par
\par
\b\fs32 RUNNING RPLIDAR\b0\fs22\par
\b\i\fs24 To find out which port RPLidar is connected to, enter this command:\par
\b0\i0\f3\fs22 ls -l /dev|grep ttyUSB\par
\f0\par
\b\i\fs24 Run the executable files:\b0\i0\fs22\par
\f3 ./simple_grabber --channel --serial /dev/ttyUSB0 256000\f0\par
\par
\b\i *You can use ultra_simple instead of simple_grabber here if you want, but I recommend using simple_grabber as it is more functional and useful than ultra_simple.\b0\i0\par
\par
\b\i *If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.\b0\i0\par
\par
\b\i *This command only ensures that RPLidar is running and the received data is displayed on the terminal. If you want to save the received data to a .txt file, follow these steps.\b0\i0\par
\par
\b\i\fs24 To create a file named veriler.txt, enter this command in the terminal:\b0\i0\fs22\par
\f3 touch veriler.txt\f0\par
\par
\b\i\fs24 To run RPLidar and save the received data to the veriler.txt file, enter this command:\b0\i0\fs22\par
\f3 ./simple_grabber --channel --serial /dev/ttyUSB0 256000 > veriler.txt 2>&1\par
\f0\par
\b\i *If you have an RPLidar A2M12, this command will work, but if you have a different version of RPLidar, change the "256000" number according to the baud rate of your Lidar.\b0\i0\par
\par
\b\i\fs24 Then simply type y in the terminal. This is a fine detail to ensure that the received data is saved to the veriler.txt file. To stop the rotation of the RPlidar, simply press the "enter" key without typing anything.\b0\i0\fs22\par
}
