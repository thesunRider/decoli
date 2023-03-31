# DEvice of COgnitive LIstening (Decoli)

## Docs
Problem Statement: [[Problem Statement]]
Questionaire: [[Questionare]]


### Requested Specifications:

| S.No | Parameters                 | Specifications                                                                                                                                            |
| ---- | -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Form factor                | Headphone/Earphone                                                                                                                                     |
| 2    | Frequency Range            | VLF to Ka band : 15khz - 40Ghz                                                                   |
| 3    | Modulation Recognition     | Automatic ,AI Assisted                                                                           |
| 4    | Power                      | <1Watts                                                                                                                                                    |
| 5    | Inbuilt Google Transalate  | Yes                                                                                                                                                      |
| 6    | Inbuilt RF fingerprinting for Channel Seperation           | Yes                                                                                                                                          |
| 7    | Battery life               | About 3 hours                                                                                                                                             |

### Design Thoughts
- There can be like two stage development cycle
	- First is where we have our SDR written from scratch
	- Second is RTL-SDR with other capabilties added to the PCB

## Maximum Specifications

Battery Voltage: 3.7V
Battery Capacity: 1000mAh = 1000mAh
Efficiency : 80%
Battery Life (FULL USE):   **Discharging Time = Battery Capacity x Battery Volt / Device Watt.**
1Ah x 3.7V * efficiency / 1W(usage-max) = 2.9Hr  

Modulation Scheme: AM Requested, FSK would be better
Data Encoding: Audio Interpolation Requested , but digital Scheme would be better as AI approach would help in better audio quality and better data security, REMEMBER we need to send additional details too.

Linux capable SOC: https://jaycarlson.net/embedded-linux/


## Approaches Available
1. Generating Carrier: (AM)
	-  The asked approach is an AM based, using MC1496 we can generate the am dsb signal
	-  We can digitally sample the the signal and multiply it using a 40khz sine wave array to yield another signal,this can be easily ssb'd
	
	For FM
	- We can use a PLL to generate the requested frequency.
	
	For ASK
	- By using a full wave bridge driver and turning it on and off ASK is achieved.

2. Amplifying the signal would be done with a push pull amplifier.
3. Impedance Matching using a transformer and senting out the signal.
5. Decoding can be done: (AM & ASK)
	- MC1496 as a Profuct detector
	
	For FM
	- A PLL can be used to regenerate the signal.

6. Recover back the Digital/Analog Signal,Play it back.

## Approach Taken
Since we have a limited amount of time going ith ASK is the best option available.
Encoding and Decoding are done using simple Serial Chips like CH340G a a baud rate of 3600bps.

### Problems Facing
- Digital or Analog Modulation
- No Tranducer in hand, in hand 40khz transducer
- In hand Transducer very low power
- AGC is needed for low powered audio signal reception


## TODO's
- [ ] Create A PCB Layout
- [ ] Create CAD Files
- [x] Breif Test Acoustic Transmitter and Reciever in Air
- [ ] Create Underwater Channel simulations

## Acoustic Communications
Recieved signal is demodulated by passing it through a BPF then through a Full wave rectifier followed by an LPF.

Driver: https://www.edn.com/increase-piezoelectric-transducer-acoustic-output-with-a-simple-circuit/

ASK Demodlator: https://www.youspice.com/spiceprojects/spice-simulation-projects/radio-circuits-spice-projects/demodulators-spice-simulation-projects/ask-demodulator/

## Light Communications

Light communication would be held using blue light sources/green light sources, 460nm blue lasers will establish communication with long targets or for surface uplinks.

![[Pasted image 20220816051546.png|500]]

![[Pasted image 20220816171746.png|300]]
Referals: https://ocean-innovations.net/companies/deepsea/knowledgebase/understanding-basics-underwater-lighting/


## Channel Simulations
https://codeocean.com/capsule/2136333/tree/v2
https://github.com/vinittech/Underwater-Broadband-Communication/blob/master/REPORT.pdf


#### Similar Products
- https://subsea-import.com/scubaphone-2000d

> Open on Obsidian for best results