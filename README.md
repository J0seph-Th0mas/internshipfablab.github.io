# 9/5/23
* learned wht AAC devices are and their functionality in the lives of people especially the people who have disabilities.
* I was able to think a viable project where people can actually learn as well as a useful device which will enhance their brain functionality.
* Did a huge amount of research on AAC devices.
* Had a meeting with the CEO of Evocube technologies
# ***

# 10/5/23
* made a presentation on the AAC device which I am going to develop.
* it is mid tech device named TalkBox which is communication device which uses tactile feeback to give auditory output
* after the presentation, i was told to start making designs for the project. 
* to make designs for this project, installed Autodesk fusion 360 to make 3D designs for my project
* downloaded ultimaker cura which is the 3D printing machine in the lab.
* [Talk Box(AAC Device).pptx](https://github.com/josephthomas8402/josephthomas8402.github.io/files/11510153/Talk.Box.AAC.Device.pptx)
# ***

# 11/5/23
* started to learn about autdesk fusion 360.
* downloaded the student version of fusion 360 and and started to learn about how to design products in fusion 360
* refered to youyube videos and the links are
* [video1](https://youtu.be/A5bc9c3S12g)
* [video2](https://youtu.be/HXRMzJWo0-Q)
* [video3](https://youtu.be/zS8dYA_Iluc)
  
# ***

# 12/5/23
* created my first 3D design which is a dice.
* printed this dice and the pic is uploaded below
* ![dice](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/bfcceb21-f5fb-4983-8ba7-aa18d864e3ef)
# ***

# 15/5/23
* Started designing the product using Fusion 360 and I was able to complete the design within tht day.
* ![sample](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/33ecd274-ac14-4b3f-beea-7336abbf68b9)
# ***

# 19/05/23
* A meeting with a former alumni was scheduled to teach us about the basics of the electronics side of the device.
* we were given links and relevant resources to prototype our device.
* we were given valuable tips on how to go about doing that.
# ***

# 22/5/23
* did a sample Audio Player Using Arduino With Micro SD Card
* ![WhatsApp Image 2023-05-22 at 15 57 09](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/8dedb17e-b6fa-4a1f-95c5-df673cf4c618)
* Many of People want to interface the SD card with arduino or want some audio output via arduino.

So here is easiest and cheapest way to interface SD card with arduino . you can use the audio output from arduino via a switch or sensor .

you can play any type of sound ,music and recording but that audio will be in to .wav file. If it is in .mp3 or any other audio type then we will convert it into .wav file.

* Step 1: Components & Requirements
```
  arduino uno
  micro SD card Adapter module
  micro SD
  Card Reader
  Speaker or earphone speaker
  woofer or amplifier
  ```
  
* Step 2: Convert Audio to .wav

 Go to the Link to convert the 
[audio into .wav](http://audio.online-convert.com/convert-to-wav)

```
Go to The Link
Upload your audio you want to convert to WAV
Change bit resolution to " 8bit ".
Change sampling rate to " 16000Hz ".
Change audio channels " mono " .
Click on " Show advanced options ".
PCM format " unsigned 8 bit ".
Convert file.
At next page click on "direct download link"
```
* Step 3: Prepare SD Card
```
 Open your SD card Drive .
Past the Audio file that we have converted in .wav file
Rename the file to "test.wav".
```
* Step 4: Add Library in Arduino
```
Open The arduino Software
Click on then Sketch >> Include Library >> Add zip Library
Select "TMRpcm.zip" that is in zip folder.
```
* Step 5: Upload the Codes

Connect your arduino with pc and upload the Codes.
```
#include "SD.h"
#define SD_ChipSelectPin 10
#include "TMRpcm.h"
#include "SPI.h"

TMRpcm tmrpcm;

void setup()
{
tmrpcm.speakerPin=9;
Serial.begin(9600);
if(!SD.begin(SD_ChipSelectPin))
{
  Serial.println("SD fail");
  return;
}
tmrpcm.setVolume(6);
tmrpcm.play("test.wav");

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

* Step 6: Circuit Connections

Insert the card in micro sd adapter module.
Connect the circuit as given below.
![circuit sd addeptor](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/0982e983-a8ff-4a02-91a0-eab9c788afc8)


```
CS ---------------------->> 10
SCK ---------------------->> 13
MOSI -------------------->> 11
MISO--------------------->> 12
VCC --------------------->> +5v
GND--------------------->> Arduino's Ground
```
Speaker Connection
one pin is in to 9 pin of Arduino and other is GND of Arduino

* Step 7: Play the Audio

Now , It's Ready...............................
Click Reset button to play audio every time.
The OUTPUT sound is very Low.
# ***

# 24/5/23
* Updated the same project but with multiple audios playing simultaneously and by one by one
* Successfully completed the task 
# ***

# 25/5/23

* As my project is RFID based, it is important that I leran what RFID is and how it works.
* So I did a small project based on RFID, which is a door locking and unlocking system..
![RFID](https://github.com/J0seph-Th0mas/internshipfablab.github.io/assets/93570559/e68e440f-b00e-43dc-9bee-fdd266e49eee)


[RFID](https://github.com/J0seph-Th0mas/internshipfablab.github.io/assets/93570559/7fbfa10f-dc38-4e51-b44c-c6d373cf8ba5)
```
* Materials:- 
Arduino UNO 
LED (Red, Green) 
RFID sensor (MFRC522) 
Servo 
Jumpers 
Breadboard 
Buzzer
```
* Circuit:- 
![RFID1](https://github.com/J0seph-Th0mas/internshipfablab.github.io/assets/93570559/e3e1353b-681b-4e43-ac55-34ad72a52c30)

* Code:- 
```
//RFID
#include <SPI.h>
#include <MFRC522.h>
#include <Servo.h>
 
#define SS_PIN 10
#define RST_PIN 9
#define LED_G 4 //define green LED pin
#define LED_R 5 //define red LED
#define BUZZER 2 //buzzer pin
MFRC522 mfrc522(SS_PIN, RST_PIN);   // Create MFRC522 instance.
Servo myServo; //define servo name
 
void setup() 
{
  Serial.begin(9600);   // Initiate a serial communication
  SPI.begin();      // Initiate  SPI bus
  mfrc522.PCD_Init();   // Initiate MFRC522
  myServo.attach(3); //servo pin
  myServo.write(0); //servo start position
  pinMode(LED_G, OUTPUT);
  pinMode(LED_R, OUTPUT);
  pinMode(BUZZER, OUTPUT);
  noTone(BUZZER);
  Serial.println("Put your card to the reader...");
  Serial.println();

}
void loop() 
{
  // Look for new cards
  if ( ! mfrc522.PICC_IsNewCardPresent()) 
  {
    return;
  }
  // Select one of the cards
  if ( ! mfrc522.PICC_ReadCardSerial()) 
  {
    return;
  }
  //Show UID on serial monitor
  Serial.print("UID tag :");
  String content= "";
  byte letter;
  for (byte i = 0; i < mfrc522.uid.size; i++) 
  {
     Serial.print(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " ");
     Serial.print(mfrc522.uid.uidByte[i], HEX);
     content.concat(String(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " "));
     content.concat(String(mfrc522.uid.uidByte[i], HEX));
  }
  Serial.println();
  Serial.print("Message : ");
  content.toUpperCase();
  if (content.substring(1) == "83 23 38 BB") //change here the UID of the card/cards that you want to give access
  {
    Serial.println("Authorized access");
    Serial.println();
    delay(500);
    digitalWrite(LED_G, HIGH);
    tone(BUZZER, 500);
    delay(300);
    noTone(BUZZER);
    myServo.write(180);
    delay(5000);
    myServo.write(0);
    digitalWrite(LED_G, LOW);
  }
 
 else   {
    Serial.println(" Access denied");
    digitalWrite(LED_R, HIGH);
    tone(BUZZER, 300);
    delay(1000);
    digitalWrite(LED_R, LOW);
    noTone(BUZZER);
  }
} 
```
* Successfully completed the project
# ***








