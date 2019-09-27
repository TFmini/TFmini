
  - 1.Functions_and_Key_Parameters
  - 2.Appearance and Structure
  - 3.Electrical Characteristics
  - 4.Line Sequence and Data Communication Protocol
  - 5.Quick Test Procedures
  - 6.Descriptions on User-defined Parameter Configuration
  - 7.Remote Upgrading
  - 8.Faults:Causes and Troubleshooting
---

# 1.Functions_and_Key_Parameters

## 1.1 Product Functions

TFmini is a mini LiDAR module. It is mainly capable of the function of real-time and contactless distance measurement and is featured by accurate, stable and high-speed distance measurement.

## 1.2 Principle of Distance Measurement

TFmini is based on TOF, namely, Time of Flight principle. To be specific, the product transmits modulation wave of near infrared ray on a periodic basis, which wave will reflect after contacting object. The product obtains time of flight by measuring round-trip phase difference and then calculates relative range between the product and the detection object, as shown in Figure1.
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019092709223170.png)

## 1.3 Key Characteristic Parameters
| Description | Parameter value |
|--|--|
| Operating Range(Indoor) |0.3m~12m  |
|  Measurement accuracy  | ±6cm@（0.3-6m）/ ±1%@（6m-12m）|
|   Default unit of distance | cm  |
|  Range resolution  | 1cm  |
|  Receiving half angle  | 1.15°  |
| Transmitting half angle   | 1.5°  |
|  Frequency |  100Hz |

## 1.4 Distance Measurement Characteristics

With optimization of light path and algorithm, TFmini has minimized influence from external environment on distance measurement performance. Despite that, the range of distance measurement may still be affected by the environment illumination intensity and the reflectivity of detection object. As shown in Figure 2:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927092731936.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)
 

 - Represents the detection blind area of TFmini, 0-30cm, within which the data is unreliable.
 - Represents the operating range of TFmini under extreme condition,which generally is 0.3-3m. Extreme condition refers to the outdoor glare (of which illumination intensity is around 100klux outdoors at  noon in summer) and detection of black target (with reflectivity of 10%).
 - Represents the operating range of TFmini for white target under normal sunshine condition (with illumination intensity of around 70klux), which covers the range of ② and is 0.3-7m.
 - Represents the operating range of TFmini at the indoor environment or considerably weak ambient light environment, which is 0.3-12m.
 - Represents the Minimum side length of effective detection for TFmini at the different distances. The data will not be stable and reliable unless “the side length of detection object” is equal to or more than the Minimum side length. The Minimum side length of effective detection depends on the FOV of TFmini (the term of FOV generally refers to the smaller value between the receiving angle and the transmitting angle), which is calculated as follows: 
 `d=2∙D∙tanβ In`
 the above formula, d is the Minimum side length of effective detection;  D is detecting range; β is the half of the value of the receiving angle of TFmini, 1.15°. Correspondence between the Minimum side length of effective detection and detecting range in general is given in Table 2.
   
|  Detecting range|  1m| 2m| 3m |4m  5m| 6m| 7m | 8m |9m |10m  | 11m | 12m |
|--|--|--|--|--|--|--|--|--|--|--|--|
| Minimum side length | 4cm |  8cm| 12cm | 16cm |20cm  |  24cm| 28cm |32cm|36cm|40cn|44cm|

# 2.Appearance_and_Structure

## 2.1 Product Appearance
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927095812631.png)

 1. Transmitting lens
 2. Receiving lens
 3. Enclosure, made of ABS+PC
 4. Mounting hole is 2.35mm through hole. ST2.9 self-tapping screw is recommended for mounting and fixing.
 5. Connecting terminal, GH1.25-4p SMT type; And along with the product there is a 10cm long connecting wire.
 6. Circuit board, without covering enclosure at the rear of product.

## 2.2 Production Structure
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927100450809.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

# 3.Electrical_Characteristics
|Description  | Parameter value |
|--|--|
|  Power supply voltage|5V  |
|  Average current| ≤140mA |
|  Peak current| 800mA |
|Average power  | ≤0.7W |
| Communication level |  LVTTL（3.3V）|

This product has no overvoltage nor polarity protection, so please make sure that connection and power supply are normal. The fluctuation of the power supply voltage in a range of ±0.1V is allowable.

Average current varies along with the operating modes of the product in two patterns, more specifically, its current is around 70mA under short distance mode and it is around 120mA under long distance mode. Please make sure that the power supply current meets the peak current of 800mA. In case of insufficient power supply current, the product maybe can’t work normally.

# 4.Line_Sequence_and_Data_Communication_Protocol

## 4.1 Description about Line Sequence and Connection
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927101130392.png)

|No.  |Pin  | Function |  Corresponding connection item| 
|--|--|--|--|
|  1|  GND|  Power supply|Power Ground  |
|2  | +5V |  Power supply|  Positive pole of power supply|
|  3|  RXD|  Receiving|  TXD|
|  4| TXD |Transmitting  |RXD  |

Type of connecting terminal: GH1.25-4P. The product includes a 10cm long connecting wire, the other end of which is a conventional 1.25-4p terminal (Molex510210400). The user may extend this wire as he/she needs. In order to ensure effective data transmission, it is recommended that the length of the connecting wire welded by the user should be less than 1m.

## 4.2 Data Communication Protocol

TFmini adopts the serial port data communication protocol, as given in Table 5.

|Communication interface  | UART |
|--|--|
|Default baud rate  | 115200 |
|  Data bit|  8|
| Stop bit |  1|
| Parity check | None |

## 4.3 Data Output Format and Code

TFmini is available with two formats of data output, namely, the standard data output format and the Pixhawk data format, both of which can be mutually switchable via the instruction command.

 - Standard data output format (default):
Data structure: each data package is 9 Byte, including the distance information (Dist), signal strength information (Strength), distance mode (Mode) and data check byte (CheckSum), etc. Data format is hexadecimal (HEX). Data codes are detailed in Table 6
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927102345559.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)
 - Serial port Pixhawk data format
The data output is in the format of character string and its unit is m(meter). For example, if the measurement distance is 1.21m, the string 1.21 will be output, followed by the escape character \r\n.

## 4.4 Descriptions of default Output Data

**Dist:** Represents the output of the distance value detected by TFmini, with the unit in cm by default. This value is interpreted into the decimal value in the range of 0-1200.In the practice, if the signal strength value- Strength<20 (which is settable), the value of Dist will be deemed as unreliable and FFFF will be output by default (-1 in case of Pixhawk data format). If Strength≥20 and actual distance >12m, the default output value of Dist will be 1,200(cm).

**Strength**：Represents the signal strength with the default value in the range of 0-3,000. After the distance mode is set, the longer the distance measurement distance is, the lower the signal strength will be; the lower the reflectivity is, the lower the signal strength will be. It is recommended that the value of Dist be deemed reliable if Strength is within the range of 20-2,000, which is adjustable by the user at his/her own discretion depending upon the scenarios of application.

**Mode**: The parameter used to indicate distance mode of the product. For this parameter, there will be some differences between different firmware versions, for 15X version of the firmware there are two modes, namely, 02 and 07, which is short-distance and long-distance operating mode respectively. The default automatic switchover logic is as the follows: if the value of signal strength is less than a certain value (generally being 70-120) under 02 distance mode, then the distance mode is switched to 07 automatically, in which case the value of Strength will be significantly increased; if the value of signal strength is more than a certain value (generally being 1,200-1,600) under 07 distance mode, the distance mode is switched to 02, in which case the value of Strength will be significantly decreased. For the 16X version, there are 3 modes 00, 03, and 07. 00 is a short distance mode, 03 is a middle distance mode, and 07 is a long distance mode. The switchover conditions for the 3 modes are similar to the 2 modes conditions described above.

# 5.Quick_Test_Procedures

## 5.1 Required Tools of Product Test
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927102558910.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 5.2 Test Procedures

 - **Download the PC software**
Please download the PC software of TFmini at our [official website](http://www.benewake.com/en/down.html).

	Caution: please shut down any anti-virus software before uncompressing the PC software. Otherwise, maybe the software is deleted as virus. The software is only runnable under Windows environment for the time being. Please refer to Attachment 1 - Product manual of TF PC software.

 - **Connection of the hardware**
Connect “TFmini”, "data wire”, “TTL - USB board” and “USB cable” as shown in Figure 6. Make sure there is no loose connection. Then connect “USB cable” with “PC”.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927102743433.png)

 - **Connection to the PC software and data output**
Open the PC software and select “①Benewake TFmini” and select automatically recognized occupied serial port (here it is “②COM9”), as shown in Figure 7

	Then click “CONNECT”. Upon successful connection, The continuous images of the output data will be displayed in area “④ TIME LINE CHART” on the right. Besides, the real-time data of the Current measure distance (Dist), effective data points per second (Effective Points) and signal strength (Strength) will be displayed in area “⑥ REAL TIME DATA” below.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927102837949.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)
**Notes:**
 - If no data is available in area “④TIME LINE CHART”, please check the line connection and line sequence. When TFmini is successfully powered on, there will be a red indicator light inside transmitting lens viewing from the front.
 - If the user want the TFmini output in the Pixhawk format, please select “③Pix Mode” at first, otherwise area “④TIME LINE CHART” will not output the right data image normally. After Pix Mode is checked, the unit of distance will be changed into m automatically. 
 - The value of distance output Dist may vary with the output unit, which is cm by default. If the unit of distance is changed to the unit-mm via an instruction, and the PC software will be unable to identify it, and so the unit of “④TIME LINE CHART” will still be cm. For example, the actual TFmini surement is 1m, the distance value of TFmini is 1000 in mm, the value read by the PC software also is 1000, but the unit will not change and still display cm.

# 6.Descriptions_on_User-defined_Parameter_Configuration
## 6.1 Function Overview
The function of user-defined configuration of product parameters is hereby enabled for more flexible settlement of your problems by TFmini. User may modify original parameters by sending relevant instructions, such as output data format and output cycle, etc. Upon successful configuration, the configured parameters will be saved in Flash without the need of reconfiguration for reboot in the event of power failure.

Please modify product configuration depending upon your actual demands. Do not frequently try irrelevant instructions so as to prevent incorrect sending of instruction which many cause unnecessary loss. Please make sure to make the configuration as per the instructions listed herein. Do not send unstated instruction.

## 6.2 Code Format of Configuration Instruction
Caution: All configuration instructions are sent as hexadecimal digits (HEX).
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927103217549.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 6.3 General Parameter Configuration and Description

Before setting the relevant parameters of TFmini, user needs to establish the connection between TFmini and PC at first. About the connection details, refer to the test connection given in 6.2. User can send the relevant configuration-related instructions to the product via TFmini PC software or other serial port debugging software. The user may also send relevant instruction by himself via his upper computer.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927103332772.png)
	

 1. Enter configuration mode by the command: 42 57 02 00 00 00 01 02
    	Echo: 42 57 02 01 00 00 01 02, indicating successful sending;
 2. Configure product parameters by the command: 42 57 02 00 EE FF GG HH
    (Table 8) 	Echo: 42 57 02 01 00 00 01 02, indicating successful  sending;
 3. Exit configuration mode by the command: 42 57 02 00 00 00 00 02
    	Echo: 42 57 02 01 00 00 00 02, indicating the successful input of the command;
      
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927103615870.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

**Explanation:**

 1. The standard data output format is given in Table 6. “Pixhawk” data  format is mainly used for the connection of Pixhawk, under which the  data output is decimal string.
 2. This configuration is mainly used for the adjustment of the output  frequency of product. Note that the value of EE FF must be integral multiple of 10; otherwise the command will be invalid. The output frequency is 100Hz (one output per 10 ms ) at max, and the minimum frequency is one output per 65530 ms. This configuration will not affect the real detection frequency of the hardware, but it only represents the frequency of data output. So the goal of power saving can’t be achieved by the means of such instruction.
3. The unit of distance output generally is cm by default and can be modified into mm. With the unit modified into mm, the distance change at level of mm is available, allowing the product to be applicable for the scenario with a single detection object and high accuracy requirement.
4. TFmini is built in with two distance modes which are automatically switchable by default. As there is a larger error during the automatic switchover of the two modes, the user may choose fixed detection pattern if there are high accuracy requirement within the limited measurement range. During the usage, please input the command for the fixed detection pattern at first and then send configuration instruction of the distance mode. The long/short distance mode configuration will become invalid once the TFmini starts the automatic switchover of distance modes. Note that for different versions of the firmware (15X means firmware whose firmware version number ends with 15X such as 152, 156, etc; 16X means firmware whose firmware version number ends with 16X such as 160, 162, etc.), and the mode configuration commands are different.
5. The range output limit is 12 meters and it is enabled by default. When the limit is disabled, the measurement data in the range of 0-15m can be output. However, the data above 12m is fitting data with significant error. So the range limit are modifiable by the user depending upon the demands. Upon the modification, the set threshold will be output if the measurement data more than such threshold 
6. The setting of minimum signal strength threshold will be valid only if ⑤ is enabled, and it is 20 by default, which means that the distance value will output FF FF if the Strength is less than 20. The user may increase such threshold in order to improve reliability of the distance measurement value. But note that the maximum threshold should be no more than 80; otherwise the LiDAR may not operate normally. Correspondingly the threshold may be decreased in order to improve the measurement range of TFmini.
7. The setting of the maximum signal strength threshold will be valid only if ⑤ is enabled. Such function is used when the user wants to set a fixed value for the near distance object detection. For e.g.:If the user has to use the TFmini within its blind area, this command can be input and then the output value of the blind area will be set to a fixed value in order to maintain a stable data.

## 6.4 Special Parameter Configuration Procedures and Description

The procedures of special parameter configuration are same as the general parameter configuration, without the need of sending the instruction for exiting configuration. The procedures are as follows:

 1. Enter the configuration mode to send: 42 57 02 00 00 00 01 02 	Echo:
    42 57 02 01 00 00 01 02, indicating successful sending;
 2. Send configuration instruction, sending: 42 57 02 00 EE FF GG HH  (for detailed instruction, refer to Table 9) 
 	Echo: 42 57 02 01 EE FF GG HH with the detailed value corresponding to the sent  instruction
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927104222764.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70) 

**Explanation:**
1. Setting of baud rate. The user may configure it upon his own communication demand.
2. There are two trigger modes for the measurement of TFmini. The default one is the internal trigger by the timer with one measurement per 10ms. The user may modify this mode into the external trigger mode which allows the TFmini to start the distance measurement by an external trigger instruction . 
Please note that the trigger frequency of TFmini should in no way be more than 80Hz as the maximum.
3.  Reset of default configuration. By sending such instruction, all adjustable configurations will be reset back to the default configurations. Please use it with caution.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927104531169.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

# 7.Remote_Upgrading

TFmini supports the remote upgrade. When the user’s product cannot satisfy the current application requirements and Benewake website has relevant firmware upgrades, the user may upgrade the product firmware via remotely upgrading the PC software .

The PC software may obtain the program version number and the product serial number by remote upgrade, and it assess whether the product needs to be upgraded. The firmware for the upgrade is contained in the zip file, and the PC software can automatically select the relative firmware for upgrade. 

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927104559611.png)

The tools for the firmware upgrade of TFmini are mostly the same as the Quick Test Procedures , which requires one TTL-USB board to connect the TFmini with PC.

Upon successful connection, open the PC software for the remote upgrade. Select appropriate port. Here it is “①COM8”. Click “② CONNECT” to connect the TFmini with the PC software. Click “③ CHECK FOR UPDATES”. The software window will show the product number and firmware version of this product, and besides it will give an upgrade prompt . However, in case of some old versions of this product, the software maybe can’t show the product number and version information, but it still supports the function of firmware upgrade. Then click “④UPGRADE” to complete upgrade.

**Caution:** please confirm that the communication bit rate of this product is 115200 before the firmware upgrade, as TFmini will be unable to upgrade at other bit rates.

# 8.Faults:Causes_and_Troubleshooting

 1. **Distance value occasionally will abruptly change into a fixed value    beyond the range during normal operation.**
	
	**Cause:** The different test environments (reflectivity of detected object, disturbance of ambient light, etc.) will affect the signal strength of TFmini. For a reliable and stable measurement data, the algorithm elimination is internally used for TFmini. In case of the insufficient signal strength, TFmini will feedback an extreme range, 12m, as a special symbol under the default condition. This value is not measurement data of TFmini, which is only used to prompt the user that such data is unreliable.
**Troubleshooting:** please use such value as the trigger signal of some unreliable data, and it will ensure that your system can use other reliable data for further assessment and decision-making if there are some unreliable data. 
 2. **Significant error between the output distant value of LiDAR and actual distance**

	**Cause ①**: Incorrect interpretation of the data communication protocol of TFmini.
**Troubleshooting**: check data communication interpretation means. In case of such error, please check the data format to adjust interpretation means.

	**Cause ②**：Due to the physical principles of TFmini, the above phenomenon is likely to occur if the detection object is the material with high reflectivity (such as mirror, smooth floor tile, etc.) or transparent substance (such as glass and water, etc.)
**Troubleshooting**: Please avoid use of this product under such circumstance in practice.

	**Cause ③**: Lens of the product are covered by the foreign matter.
**Troubleshooting**: please use dry dust-free cloth to gently remove the foreign matter

 3. **TFmini fails to output data**

	**Cause**: The product will be strictly inspected before leaving our factory, ensuring that all the shipped products can work normally. However, some abnormal working matters maybe still occur because of incidents during the transportation or use.
**Troubleshooting**: Check whether the power supply is normal; check whether the voltage is within rated voltage range. If power supply is normal, there will be a red light inside the transmitting lens of TFmini.
Check TFmini with correct connection sequence and reliable connection.
Check whether the data interpretation is correct. Please carry out the interpretation as per the data format specified herein.
If the problem persists, please contact our technical support.

 4. **There is no data output when LiDAR is connected to PC software.**

	**Cause ①**: The PC software only supports the Windows operation system for the time being
**Troubleshooting**: Use the PC supporting Windows operation system.

	**Cause ②**: TTL - USB board is poorly connected.
**Troubleshooting**: Check the TTL -USB board with the correct and reliable connection with TFmini and PC.

	**Cause ③**: Driver of serial port is not correctly installed.
**Troubleshooting**: Plug and unplug USB cable again. Try to reinstall the driver or directly download and install a driver from the internet.
If the PC software still work abnormally, please contact our technical support.
