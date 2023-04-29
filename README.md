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
	
Our main agenda is to create a device with the smallest size possible. We will add the software features later down the development line.
## Maximum Specifications

Battery Voltage: 3.7V
Battery Capacity: 1000mAh = 1000mAh
Efficiency : 80%
Battery Life (FULL USE):   **Discharging Time = Battery Capacity x Battery Volt / Device Watt.**
1Ah x 3.7V * efficiency / 1W(usage-max) = 2.9Hr  

Linux capable SOC: https://jaycarlson.net/embedded-linux/

## Approach Taken
We have first moved forward with creating a prototype with discreate RTL sdr and Raspberry Zero W, We have implemented all baseline algorithms and tested it on real hardware thus proving initial tests, We have created a PCb layout which have all these discrete componets packed into a single set. Thus making the sie compact.Need to get the PCB manufactured and assembled.

### Problems Facing
- Modulation Detection needs more processing Power
- Faster processing needs processor overclockng leading to increased heat
- Ultra small Display resolution
- Explore Other ways to represent data than water fall charts 
- AGC is needed for low powered audio signal reception


## TODO's
- [x] Create A PCB Layout
- [x] Create CAD Files
- [x] Breif Test Reciever in Air with base Code
- [ ] Prototype a PCB
- [ ] Implement Full Code

## Acoustic Communications
Recieved signal is demodulated by passing it through a BPF then through a Full wave rectifier followed by an LPF.

Driver: https://www.edn.com/increase-piezoelectric-transducer-acoustic-output-with-a-simple-circuit/

ASK Demodlator: https://www.youspice.com/spiceprojects/spice-simulation-projects/radio-circuits-spice-projects/demodulators-spice-simulation-projects/ask-demodulator/


#### Similar Products
- https://swling.com/blog/tag/portable-sdrs/
- https://www-rtl--sdr-com.webpkgcache.com/doc/-/s/www.rtl-sdr.com/
- https://www.rtl-sdr.com/raspad-3-0-review-building-a-portable-raspberry-pi-4-tablet-with-built-in-rtl-sdr/

> Open on Obsidian for best results
