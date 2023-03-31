## Script
> Your presentation duration will be 10 minutes (5 minutes for presenting your slides + 5 minutes for Q&A).

- SLIDE1

![[slide1_1.webm]]
> Hi everyone,Suryasaradhi here, I am here today to do my presentations on the Underwater communications category, Our Innovation is called MVUS or Messaging and Voice for Underwater Systems.

- SLIDE 2
![[slide2_1.webm]]
> The proposed solution is a hybrid underwater communication technology which uses light,radio and sound waves to send your message far and through the ocean

![[slide2_2.webm]]
> We are using an AI technology called LYRA which enables us to establish a digital audio communication channel between the users without a compomise in quality

![[slide2_3.webm]]
> You can see our envisioned product on this Render,  A Tranciever is attatched to the divers head which uses light and sound to send and recieve data omnidirectionally, An armband controller attatched to his hand helps to view and change who you are communicating with, To the neck we have a sensor for reading the divers vitals and a laryngophone which acts as an underwater microphone,to the back we have a control centre which connects all these parts together , this section also holds the battery and the RF transciever.


![[slide2_4.webm]]
> We have not yet created a complete device, instead we have breadboarded small functional blocks of all the transmission systems in hopes of testing out our circuit and gathering some data from it.
>
> We here have the optical transciever ,where we have used a 50mw LED ,here the system is capable of sending data upto 2meter underwater,Similarly we have an acoustic transciever capable of sending signals upto distance of around 15m underwater.
> 
> Both the LED and the transducer used are low powered ones, less than around 60mW peak power, Hence the low range,but the circuit have been designed to scale up its output power to about 18W ,this simply means we have to replace these low powered transducers with a high powered counterpart to scale its distance to the Kilometer range,the same goes for optical transciever too.

- SLIDE 3

> We have created a half duplex dual sideband suppressed carrier system with adjustable modulation index for power efficiency.
> The maximum deliverable power by the system is 18Watts, the acoustic system being a class AB amplifier with a -20dm second harmonic,the system offers a range of 3km with a 117db with respect to air, 28khz transducer
> An analog AGC normalizes the recieved signal and a software  pitch  controller tunes the users speech 
> Another Advantage of the system is the use of digital communication where we are able to keep our communication channel secure. This also reduces the impact of distortion on data transfer by the medium.
> Although our acoustic bandwidth is limited we are using Light to transmit large data faster.
> Usage of AI technology like Lyra helps us to encode audio in only 3kilobits bitrate ,this offers us high fidility realtime audio streaming.
> We have prototyped individual functional blocks
> We do have several competitiors in the field, but no one offers high fidelity secure audio,all rely on analogue audio for communication.
> We are targeting the system for, Navy,All underwater Operators and for Search and Rescue missions
