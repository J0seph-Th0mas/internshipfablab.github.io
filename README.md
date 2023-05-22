# DAY 1(9/5/23)
* This day I was able to learn about wht AAC devices are and their functionality in the lives of people especially the people who have disabilities.
* I was able to think a viable project where people can actually learn as well as a useful device which will enhance their brain functionality.
* Did a huge amount of research on AAC devices.
* Had a meeting with the boss of Evocube technologies
# end of day 1

# Day 2(10/5/23)
* well, on this day I mde a presentation on the AAC device which I am going to develop.
* it is mid tech device named TalkBox which is communication device which uses tactile feeback to give auditory output
* after the presentation, i was told to start making designs for the project. 
* to make designs for this project, I had to install Autodesk fusion 360, wher I could make 3D designs for my project.(took a very long time to download)
* After that i downloaded ultimaker cura which is the 3D printing machine in the lab.
* Downloaded a few 3d models from from the internet to trty out in the 3D printer but I was unable to due to time constraints
* [Talk Box(AAC Device).pptx](https://github.com/josephthomas8402/josephthomas8402.github.io/files/11510153/Talk.Box.AAC.Device.pptx)

# end of day 2

# Day 3(11/5/23)
* On day 3 i started to learn about autdesk fusion 360.
* i download the student version of fusion 360 and and started to learn about how to design products in fusion 360
* i refered to youyube videos and the links are https://youtu.be/A5bc9c3S12g https://youtu.be/HXRMzJWo0-Q and https://youtu.be/zS8dYA_Iluc
# end of day 3

# Day 4(12/5/23)
* And I created my first 3D design which is a dice.
* and I printed this dice and the pic is uploaded below
* ![dice](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/bfcceb21-f5fb-4983-8ba7-aa18d864e3ef)
# end of day 4

# Day 5(15/5/23)
* Started designing the product using Fusion 360 and I was able to complete the design within tht day.
* ![sample](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/33ecd274-ac14-4b3f-beea-7336abbf68b9)
# end of day 5

# Day 6(22/5/23)
* did a sample Audio Player Using Arduino With Micro SD Card
* ![WhatsApp Image 2023-05-22 at 15 57 09](https://github.com/josephthomas8402/josephthomas8402.github.io/assets/93570559/8dedb17e-b6fa-4a1f-95c5-df673cf4c618)
* Many of People want to interface the SD card with arduino or want some audio output via arduino.

So here is easiest and cheapest way to interface SD card with arduino . you can use the audio output from arduino via a switch or sensor .

you can play any type of sound ,music and recording but that audio will be in to .wav file. If it is in .mp3 or any other audio type then we will convert it into .wav file.

* Step 1: Components & Requirements
  arduino uno
  micro SD card Adapter module
  micro SD
  Card Reader
  Speaker or earphone speaker
  woofer or amplifier
  
* Step 2: Convert Audio to .wav


  Go to the Link to convert the audio into .wav .
http://audio.online-convert.com/convert-to-wav
Go to The Link
Upload your audio you want to convert to WAV
Change bit resolution to " 8bit ".
Change sampling rate to " 16000Hz ".
Change audio channels " mono " .
Click on " Show advanced options ".
PCM format " unsigned 8 bit ".
Convert file.
At next page click on "direct download link"

* Step 3: Prepare SD Card

 Open your SD card Drive .
Past the Audio file that we have converted in .wav file
Rename the file to "test.wav".

* Step 4: Add Library in Arduino

Open The arduino Software
Click on then Sketch >> Include Library >> Add zip Library
Select "TMRpcm.zip" that is in zip folder.

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
![Uploading circuit sd addeptor.jpg…]()


CS ---------------------->> 10
SCK ---------------------->> 13
MOSI -------------------->> 11
MISO--------------------->> 12
VCC --------------------->> +5v
GND--------------------->> Arduino's Ground

Speaker Connection
one pin is in to 9 pin of Arduino and other is GND of Arduino

* Step 7: Play the Audio

Now , It's Ready...............................
Click Reset button to play audio every time.
The OUTPUT sound is very Low so you can use woofer or amplifier for batter Output.

# end of day 6




