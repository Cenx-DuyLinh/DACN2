# Acquiring 15 m/s cruise speed
---
[Sheet link](https://docs.google.com/spreadsheets/d/1Ys8nD785RTRev7et7yYlS1L4-2iYJHopqZFAbuxZgvw/edit?usp=sharing)
Given information: 
- Cruising height around 30m (Relative to the land below)
- The airplane will be the tilted-rotor unmanned aerial vehicle (TRUAV)
- The hardware can either be:
	- The old TRUAV from các anh Thịnh, Cường, Lợi 
	- ~~Buying an empty airframe and then work from there~~
## 1. Getting the old TRUAV
Since the airplane is already built an it has a cruise speed of 19m/s (worst case is that we will only get the old frame and nothing else) we need to redesign it, making the lift at 15m/s equal to the lift at 19m/s

TL;DR: **Decrease the cruise speed** 

> So how are we going to do it ? 
- Increase the lift coefficient of the aircraft
	1. ~~Reduce the weight of the aircraft ~~
	2. Increase the angle of attack of the aircraft (Note: AOA can change to maximum ~6deg, [[NguyenGiaThinh|Reason why]])
	3. Add high-lift component:
		- Attach a leading edge device (Nose flaps, Kruger flaps, and slats)
		- Other stuff
		- Others: [Source to this stuff](https://www.ae.utexas.edu/courses/ase463q/design_pages/summer02/activewing/page009.html)
	4. Adjust the angle of the 2 titled rotor so it can add lift
### 1.1 Increase the AOA of the wing
>We need to calculated the Cl.cruise need for flying 15m/s
- Original Cl.cruise: Cl = 0.5074 (35m ASL, 25C, 19m/s)
- JIC Cl.cruise : Cl = 0.531 (960m ASL, 6C, 19m/s)
- JIC Cl.cruise but at 15m/s, as we can see there is a difference of about 0.32 in Cl when flying at 15m/s compare to 19m/s
![Uploading file...7ku1j]()


- Based on the the simulation in XFLR5 at Reynold = 309146, the AOA of the wing should increase to ~5 degree for enough Cl.cruise
![](https://i.imgur.com/4gHTYWA.png)

### 1.2 Add high-lift components

Because the flaps of the airplane is located at 25% of the MAC
![](https://i.imgur.com/GOHMB1p.png)
We can apply to the formula below:

**Source:** *Hansen, M. O. L. (2008). Aerodynamics of Wind Turbines (2nd ed.). Earthscan Publications Ltd.*

![](https://i.imgur.com/eSqyVfN.png)

![](https://i.imgur.com/MFwnZF9.png)

![](https://i.imgur.com/LbsEZA3.png)

![](https://i.imgur.com/YoHVBQw.png)

![](https://i.imgur.com/Dec6g9A.png)

![](https://i.imgur.com/PRmMttS.png)

![](https://i.imgur.com/2IP8Wqx.png)

The increase in lift coefficient are calculated in the [Sheet link](https://docs.google.com/spreadsheets/d/1Ys8nD785RTRev7et7yYlS1L4-2iYJHopqZFAbuxZgvw/edit?usp=sharing), we can see that there is a small increase (maximum of about 0.28) in the Cl.cruise
![](https://i.imgur.com/vpg41Ui.png)

However we must also consider the increase in drag when doing this
### 1.3 Adjust the angle of the 2 titled rotor


~~### Buying new empty frame~~

# Increase the flight time to satisfy flight mission
---
## Known information: 
* The TR-VTOL's battery: 1 * 6S 16000 mAh
* The aircraft MTOW = ~64 N
* At hover mode the average of aircraft current usage: ~63 A 
* The aircraft are equiped with: 
	* 2 Sunnysky X3520 - 520 KV with XDL 14 * 8 in propellers (front)
	* 1 Sunnysky X6212S - 300KV with 22 * 6.6 in propeller (rear)
	*  And other electric components (Flight controller, servo, GPS,...)
* There are no data on level flight mode's electricity consumption (From previous report of TR-VTOL).
* The camera we intended to use: [FLIR Vue Pro 336 30Hz Thermal Imaging Camera](https://www.tester.co.uk/flir-vue-pro-336-30hz-thermal-imaging-camera-choice-of-lens)
* Video transmitter we intended to use: *Not yet selected*
## Calculating the operation time of the TR-VTOL
### Hover mode
From the report of previous generation, we have the information about the electricity usage of the aircraft in hover configuration.
![](https://i.imgur.com/JfLilUl.png)
The current usage of the aircraft is approximately ~63 A
Then we can estimate the maximum endurance time in hover mode using equation:
>Time(min)=(Battery capacity (Ah)* 0.8)/Current usage(A)) * 60

Maximum endurance time in hover mode ***Time =~ 12 minutes***
(This estimation depend only on already known data)
### Level flight mode
Since there are no report on the current usage of the aircraft on level flight mode. We have to estimate the current usage using data from the manufacturer.
From the report of Mr.Thinh, we obtain the CL/CD data table of the aircraft and their relationship equation:
![](https://i.imgur.com/o6iJbyO.png)
![](https://i.imgur.com/oCauLOZ.png)

At level flight condition we have:
![](https://i.imgur.com/15Ye7sN.png)
[Source: Thrust and Power Required (agodemar.github.io)](https://agodemar.github.io/FlightMechanics4Pilots/mypages/thrust-power-required/)

In short, required thrust for level flight condition can be found using equation:
> Thurst (N) = Weight (N) / (CL/CD)

With input:
* CL = 0.85 (From Lĩnh calculation)
* Weight = 63.739 N
We can calculate the required thrurst:
![](https://i.imgur.com/ZnkEnff.png)
This mean that each front motor need to generate 2.86 N of thrust
Then from the data sheet of motor Sunnysky X3520 - 520 KV with XDL 14 * 8 inch propellers 
![](https://i.imgur.com/yDfaObP.png)
![](https://i.imgur.com/XEodFKu.png)

=> Take the average usage current, we find that each motor required ~ 26 A to generate 2.8N of thrust
Then we can estimate the maximum endurance time in level flight mode using equation:
>Time(min)=(Battery capacity (Ah)* 0.8)/Current usage(A)) * 60

![](https://i.imgur.com/LszU609.png)

***=> The estimated endurance of the aircraft in level flight mode is about 15 minutes***
## The relationship between FOV and mounting angle of TI cam
![](https://i.imgur.com/QSFPAcq.png)
By increase the φ angle of mounted camera, we can increase the maximum scanning area while also increase the chance to discover heat source that hidden below the dense forest environment. However, doing so will make the shape of the further pixel distorted (as in picture above) ->Thus reduce the accuracy of the heat signal reading.

It is stated in the [Optimising observing strategies for monitoring animals using drone-mounted thermal infrared cameras. (researchgate.net)](https://www.researchgate.net/publication/329390751_Optimising_observing_strategies_for_monitoring_animals_using_drone-mounted_thermal_infrared_cameras) that "The minimum diameter for accurate identi cation of an object (or species of animal) and measurement of its temperature is 10 pixels for most TIR cameras."

Equation to determine the shape of each pixel is given below:
![](https://i.imgur.com/RYK1xSL.png)
![](https://i.imgur.com/v6rAnWM.png)
Source: [(PDF) Optimising observing strategies for monitoring animals using drone-mounted thermal infrared cameras. (researchgate.net)](https://www.researchgate.net/publication/329390751_Optimising_observing_strategies_for_monitoring_animals_using_drone-mounted_thermal_infrared_cameras)

## Calculate the total required endurance time:
According to the flight mission, the minimum required endurance for the aircraft to cover whole area of competition location (1000ha) is approximately ~ 14 hrs. This approximation haven't account for the altitude, terrain variation in the competition area and the overlapping scanning area in reality.
***=> This approximation is calculated at h = 30 m, V = 15 m/s and the camera is mounted at 90 degree angle
=> The estimated number of pixels on a person at this condition is about 515 pixel^2***

There are some change we can make in order to reduce the required endurance flight time:
- Increase the searching altitude of the aircraft. -> Increase scanning area
- Increase the cruise speed of the aircraft.
- Optimize flight plan to increase chance of finding target.
***+ For example: If V = 20 m/s and h = 50m
=> The required time for operation is 6,26 hrs and the estimated pixel on person is 185,48 pixel^2***

# Flight mission
---
The flight mission is based on the Japan-innovation-challenge (JIC2023) flight profile. 

![](https://i.imgur.com/4xCA4Ei.png)

- **Big circle in the middle:** Competition Area
- **Little tent at the middle:** Control Area

Going to google map, we can see that the distant are listed as follow:
![](https://i.imgur.com/CUwBo30.png)

- Diameter: ~10km 
- Area: ~1000ha 
Assuming that the plane is flying at a height of 30m, we can calculate as in the sheet describe  [Sheet link](https://docs.google.com/spreadsheets/d/1Ys8nD785RTRev7et7yYlS1L4-2iYJHopqZFAbuxZgvw/edit?usp=sharing)

![](https://i.imgur.com/EXyZKbp.png)




# Problem statement
---
[[1.1 Project Introduction]]

[[1.2 Project Objective]]

[[1.3 Problem to be solve]]