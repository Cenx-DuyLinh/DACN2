# Acquiring 15 m/s cruise speed
---
Given information: 
- Cruising height around 30m (Relative to the land below)
- The airplane will be the tilted-rotor unmanned aerial vehicle (TRUAV)
- The hardware can either be:
	- The old TRUAV from các anh Thịnh, Cường, Lợi 
	- Buying an empty airframe and then work from there
### Getting the old TRUAV
Since the airplane is already built an it has a cruise speed of 19m/s (worst case is that we will only get the old frame and nothing else) we need to redesign it, making the lift at 15m/s equal to the lift at 19m/s

TL;DR: **Decrease the cruise speed** 

> So how are we going to do it ? 
- Increase the lift coefficient of the aircraft
	1. ~~Reduce the weight of the aircraft ~~
	2. Increase the angle of attack of the aircraft (Note: AOA can change to maximum ~6deg, [[NguyenGiaThinh|Reason why]])
	3. Add aerodynamics component:
		- Attach a leading edge device (Nose flaps, Kruger flaps, and slats)
		- Other stuff
		- Others: [Source to this stuff](https://www.ae.utexas.edu/courses/ase463q/design_pages/summer02/activewing/page009.html)
	4. Adjust the angle of the 2 titled rotor so it can add lift

>We need to calculated the Cl.cruise need for flying 15m/s
- Original Cl.cruise: Cl = 0.5074 (this is at 35m above sea level and 25C)
- Calculating that Cl.cruise but at the competition zone (This is base on the assumption that the weather is extreme)

| Type                     | Value     | Unit  |
| ------------------------ | --------- | ----- |
| Mach number              | 0.04479   | -      |
| Height                   | 1000      | m     |
| Temperature              | 6         | C     |
| Density                  | 1.1218    | kg/m3 |
| Reynold numbers          | 301817    | -     |
| Dynamic viscosity        | 1.773 E-5 | kg/ms |
| Cl.cruise at 19m/s - 30m | 0.5074    | -     |
| Cl.cruise at 15m/s - 1km | 0.8574    | -     |
 
![](https://i.imgur.com/DwQFbG5.png)

- Based on the the simulation in XFLR5 at Reynold = 301817, the AOA of the wing should increase to ~5 degree for enough Cl.cruise
![](https://i.imgur.com/4gHTYWA.png)



### Buying new empty frame

# Increase the flight time to satisfy flight mission
---
### Known information: 
* The TR-VTOL's battery: 1 * 6S 16000 mAh
* At hover mode the average of aircraft current usage: ~63 A 
* The aircraft are equiped with: 
	* 2 Sunnysky X3520 - 520 KV with XDL 14 * 8 in propellers (front)
	* 1 Sunnysky X6212S - 300KV with 22 * 6.6 in propeller (rear)
	*  And other electric components (Flight controller, servo, GPS,...)
* There are no data on level flight mode's electricity consumption.
* The camera we intended to use: [FLIR Vue Pro 336 30Hz Thermal Imaging Camera](https://www.tester.co.uk/flir-vue-pro-336-30hz-thermal-imaging-camera-choice-of-lens)
* Video transmitter we intended to use: *Not yet selected*
## The required endurance time:
* According to the flight mission, the minimum required endurance for the aircraft to cover whole area of competition location (1000ha) is approximately ~ 45 mins. This approximation haven't account for the altitude and terrain variation in the competition area.



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
Assuming that the plane is flying at a height of 30m, we than have:

| Value                                 | Amount                 |
| ------------------------------------- | ---------------------- |
| FPS                                   | 30                     |
| Flying speed                          | 15m/s                  |
| Camera view                           | 2α = 65                |
| Height flying compare to the ground   | 30m                    |
| Radius of the circle                  | 56.7m                  |
| The area that the camera see (square) | 6430m2                 |
| The length of that square             | 40.1m                  |
| Time flying for 6430m2                | 2.673s                 |
| Time to flying for 1000ha             | 1555s = 26min ~= 45min |

