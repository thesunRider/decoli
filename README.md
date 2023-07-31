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

## Anteena Specs

Switched through SPDT Switch

20khz - 20mhz -> Ferrite Rod Anteena
10mhz - 100mhz -> ?
100mhz - 1 Ghz-> Wire based dipole anteena
100mhz - 1Ghz -> chip anteena
2ghz - 10ghz -> Chip anteena
Wifi -> Chip Anteena

## Design Inspiration

RTL SDR ->  Taken from Datasheets
Linux Subsystem ->
Wifi Module -> ESP8266

Since R820T Doesnt have HF Specs we need to use a Hardware mod that directly connects the amplified signal to HF band. (mentioned in URL), We have devised a 9db common base amplifier to amplify the HF band to feed to rtlsdr

We have designed seperate schematic board for 20khz - 20mhz and 1ghz - 10ghz bands
This allows us to either create specific board or hats if required or incorporaste into the final board , away from the main control systems.

0.6Ghz - 3.1 Ghz : SR4L054
3Ghz - 10Ghz : 3100AT51A7200001E

RF Amp and switcher: ADL8112
Attentuator: TGL4203-SM
RF Preamp: [HMC788ALP2E](https://www.digikey.in/en/products/detail/analog-devices-inc/HMC788ALP2E/5268980)
VLF Active anteena : [An Active Ferrite Rod Antenna with Remote Tuning](38815473.pdf)
10Ghz LP: LFCW-8700+
48 Mhz BPF: BPF-B48+
75 Mhz BPF: BPF-B76+

## Specifications

#### R820T Tuner:
- Frequency range: 25 to 1766 MHz
- Noise figure : 3.5 dB @ RF_IN
- Phase noise: -98 dBc/Hz @ 10 kHz
- Current consumption: ＜178 mA @ 3.3V power supply
-  Max input power: +10 dBm
- Image rejection: 65 dBc

#### RTL232 DSP:

- Differential input impedance of the RTL 283 chip is approximately 3,300 Ohms

Oscillator : MAX2871
Layer stackup should be 4 layer with: RF DC, GND, RF DC, GND
Using Si5351A for XREF generation

## Reference URL

RTL SDR HF Hardware MOD: https://www.rtl-sdr.com/an-interesting-rtl-sdr-direct-sampling-modification/
RTL SDR HF Hardware MOD implemented: https://www.g8jnj.net/softwaredefinedradio.htm
Using RTL SDR over stm32 microcontroller: https://fallingnate.svbtle.com/rtl2832-usb-stm32-pt1
Linux capable SOC: https://jaycarlson.net/embedded-linux/
RTL SDR base design: https://www.rtl-sdr.com/forum/viewtopic.php?f=1&t=265#p824
Generalised Block Diagram: https://aaronscher.com/wireless_com_SDR/rtl_sdr_info.html
Ferrite rod calculator: https://coil32.net/online-calculators/ferrite-rod-calculator.html
LPA and sa602 reference design: https://web.archive.org/web/20161031125636/http://home.scarlet.be:80/on1bes/sdr_up_converter3.0_r820t.html
Good RF Downconverter: https://github.com/raziele/Nigun , https://www.rtl-sdr.com/nigun-open-hardware-plans-for-an-rtl-sdr-downconverter/
1.5 to 6ghz Downconverter: https://github.com/electrosense/hardware/tree/master/electrosense-converter-firmware , https://www.rtl-sdr.com/electrosense-rtl-sdr-based-crowd-sourced-spectrum-monitoring-with-a-dc-to-6-ghz-rtl-sdr-up-downconverter/
50mhz to 12Ghz PLL VCO: https://www.digikey.in/en/products/detail/analog-devices-inc/ADF5610BCCZ/10249599
Devkit VCO above: https://www.analog.com/en/products/adf5610.html#product-evaluationkit
XREF Generator using Si5351A: https://learn.adafruit.com/adafruit-si5351-clock-generator-breakout/downloads
Wideband Anteena: https://www.digikey.com/en/products/detail/johanson-technology-inc/3100AT51A7200E/1840080 [3.1-10.3 Ghz]
Wideband Anteena Low Freq: https://www.digikey.in/short/z9rwv9qc [0.6 - 3.1 Ghz]

## Circuits Used:

![[Pasted image 20230725235952.png]]

![[Pasted image 20230724040329.png]]


![[Pasted image 20230723232849.png]]

### Block Diagram

![[Pasted image 20230723230714.png]]


> Open on Obsidian for best results
