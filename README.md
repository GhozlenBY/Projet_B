# Projet_B

                                ![image](https://github.com/GhozlenBY/Projet_B/assets/148441001/b26ed8a3-ee41-4f1d-9e10-154ca0822863)

# Projet Overview:
The purpose of this project is to create a system capable of counting electronic components based on image recognition and classification. This device uses an Arduino Nano 33 BLE board and an OV7670 camera.

The electronic components to be counted are placed on a work surface and move individually every two seconds (their movement is done manually). The system performs recognition using a Deep Learning model trained previously with TensorFlow Lite or Edge Impulse.

After classification, the data is transmitted via Bluetooth Low Energy (BLE) to Node-RED, which is responsible for counting and presenting them on an interactive dashboard.
