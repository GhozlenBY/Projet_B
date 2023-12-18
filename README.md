# Projet_B: 

                                ![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/b26ed8a3-ee41-4f1d-9e10-154ca0822863)

# Projet Overview:
The purpose of this project is to create a system capable of counting electronic components based on image recognition and classification. This device uses an Arduino Nano 33 BLE board and an OV7670 camera.

The electronic components to be counted are placed on a work surface and move individually every two seconds (their movement is done manually). The system performs recognition using a Deep Learning model trained previously with TensorFlow Lite or Edge Impulse(https://github.com/GhozlenBY/-Electronic-components-dectetors).

After classification, the data is transmitted via Bluetooth Low Energy (BLE) to Node-RED, which is responsible for counting and presenting them on an interactive dashboard.

# Test the example on the board
The first step is to integrate the Deep Learning model onto the Arduino Nano 33 BLE board. This can be achieved using the library downloaded from Edge Impulse.

![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/934116e9-c272-4066-b442-1ab9201f12c0)

To count the components, you can add a loop within the loop function and define the five categories.
![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/9b08ff44-69b6-4a34-92d2-90b9ca083491)

# Setting the BLE
This sketch from the Arduino BLE library provided crucial insights for our project. It helps control the onboard LED of the Arduino Nano BLE 33 based on a connected button's state on pin 4. Notably, it sends LED and button state notifications via Bluetooth for monitoring through the Light Blue app.

![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/cce915df-dfaa-4c78-bc37-d110dba9cce1)

# Connection with NOde Red
First we need to download Node Red on the machine or a Raspberry Pi.
Then, to perform data transmission between the Arduino and Node-RED, you need to download the "ble-sense" packages using this command.
![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/44d7f13d-7e95-42e2-b7ba-afddb0cb8b8a)

The package contains two nodes: BLE Scanner, BLE Connect.

BLE Scanner node allows you to scan BLE devices. A message with start as a topic starts scanning. The node can output the following:

- Whole peripheral as an object.
- The MAC address of the peripheral.
- The advertisement data as a buffer array.
- Hence BLE Scanner node can be used as an observer. This node also allows you to configure and search for a specific peripheral via given name. To stop scanning a message with stop topic should be given.

BLE Connect node provides direct connection to the peripheral. This node must not be used alone. The scanning should be in progress to establish a connection. It takes JSON Object as an input. The service and characteristics UUIDs should be provided. If not, it will try to subscribe all advertised characteristics.

so to establish the connection you run Node red and connect these nodes:
![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/87472a5a-e434-4c14-9d07-ae494dea34d1)

![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/aa11fc60-8729-473f-a1d6-6eb52776b86c)








