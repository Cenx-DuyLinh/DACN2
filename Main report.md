# Problem statement

## ABSTRACT
Tilt Rotors Vertical Take-off and Landing Unmanned Aerial Vehicles (TRVTOL-UAVs) have the potential to be the next generation of UAVs due to their ability to operate like a helicopter while also being able to function like a conventi onal fixed-wing aircraft. Combined with the use of a tilting rotors mechanism can increase the efficiency of the VTOL-UAVs significantly, thus making it suitable for a variety of missions.
Overall, this specialized project goal is to study the basic operating principles of the TRVTOL-UAV configuration, along with the report from Tran Duy Linh, we conduct multiple tests and re-evaluation of the already built Tri copter-TRVTOL-UAV received from the Aerospace engineering department. The final goal of this specialized project is to suggest improvement in the design of a more efficient TRVTOL-UAV. 
In this report, I want to focus on evaluating the overall frame structure, the electrical system, and the flight characteristics of the old TRVTOL-UAV. Then, find out what change can be made to improve the performance of the aircraft. Finally, a newly improved frame structure of the TRVTOL-UAV configuration will be presented at the end of the report.
(Mẫu Abstract của tt)
## Project introduction
---

In recent years, interest in Vertical Take-Off and Landing (VTOL) Unmanned Aerial Vehicles (UAVs) has significantly increased due to advancements in technology. Hardware components such as motors, electronic parts, and batteries have become lighter, more compact, and higher performing. Flight controller computational units are now available in various sizes with increased computational speed and storage capacity. Furthermore, developments in material technologies have led to the creation of lighter, stronger composite materials at reduced production costs. Altogether, these advancements have created a thriving market for commercial-grade UAVs across multiple industries, including aerial surveillance, search and rescue operations, transportation, etc.

(Hinh ung dung cua UAV trong cac mission khac nhau)

Among popular UAV designs, there are typically three main configurations: the hovering/helicopter design, the fixed-wing design, and the hybrid design. Hybrid UAVs provide a unique combination of vertical take-off and landing capabilities, similar to a helicopter, while also offering extended cruising abilities similar to fixed-wing aircraft. However, despite having the advantages of both helicopter and fixed-wing designs, the hybrid UAV does have its own disadvantages.

(Bang so sanh giua 3 loai may bay)

Throughout the developmental history of VTOL-UAVs, various conceptual designs have emerged, primarily differing in how thrust vectors are applied and the transition methods between hover and cruise modes. Despite these differences, their overarching objective remains consistent: maximizing the efficiency of hybrid UAVs. In summary, these hybrid conceptual designs can be categorized into four main configurations based on the number of thrust inputs they employ.

(Hinh va chu thich cho cac cau hinh may bay hybrid)

In this specialized project report, our focus centers on the tri-copter configuration of hybrid UAV design. As implied by its name, this UAV setup incorporates three thrust inputs. Most tri-copter designs feature two front rotors, similar to the dual-copter design, the addition of a third rotor at the rear of the aircraft enhances stability and control. As a result, this setup allows simpler vertical takeoff and landing maneuvers compared to the dual-copter configuration. At the same time, during level flight, the tri-copter configuration generates less drag than a quad-copter configuration design. 
The transition to level flight is usually executed by tilting the forward propellers, propelling the hybrid craft forward while maintaining vertical lift through thrust. To retain pitch equilibrium during this phase, a combination of tail thrust and elevator deflection is utilized. Notably, both the tail thrust and elevator serve as redundant systems, offering the flexibility to employ them independently or in a blended manner. More detail on the stability characteristic of the tri-copter configuration will be reviewed in Chapter 3 of this report.



## Project objective 
---
The primary objective of this project is to conduct analyzation of the Tilt-rotors VTOL UAV, previously constructed by Nguyen Gia Thinh, Trinh Vinh Loi , and Pham Minh Cuong, to conduct extensive research to modify the aircraft for the purpose of operating as an emergency surveillance platform. 
The aim is to assist rescue operations specifically in densely forested regions. By utilizing the combined advantages of fixed-wing aircraft and rotorcraft, these UAVs are capable of vertically taking off, hovering, and landing similar to a helicopter, while also enabling extended cruising flights comparable to those of conventional fixed-wing aircraft. This versatile capability is a fundamental characteristic that make them suitable for successful execution of large-scale area rescue missions.

![](https://i.imgur.com/85Xs37F.png)
TRUAV from predecessor
Source: N. G. Thinh. "THIẾT KẾ VÀ THỬ NGHIỆM CHO MÁY BAY CÁT VÀ HẠ CÁNH THẲNG ĐỨNG SỬ DỤNG CƠ CẤU CHONG CHÓNG XOAY- XÂY DỰNG MÔ HÌNH ĐỘNG LỰC HỌC VÀ ĐIỀU KHIỂN ", Ho Chi Minh, 2022

In this project, we will based on the scenario of the Japan Innovation Challenge (JIC) 2023. The main objective of this competition is to promote research and development in conducting unmanned vehicle operations to save lives during disasters, particularly in dense and hard-to-reach locations like mountains and forests.
The competition consists of three challenges: "Discovery," "Transportation," and "Rescue." These challenges involve locating mannequins, delivering rescue packages, and retrieving mannequins using robots, respectively. In our project, we will primarily focus on the initial challenge, which involves identifying and localizing these mannequins in bad environmental conditions. These conditions are characterized by harsh weather and heavy rainfall.
![](https://i.imgur.com/7pWNvk4.png)
Banners of the Japan Innovation challenge 
Source: https://japan-innovation-challenge.com/en/

The challenge competition area will take place near the region mountain Setayama, Kamiotofuke, Kamishihoro, Kato District, Hokkaido 080-1407, Japan. Based on the document given by the committee, we can evaluate roughly some of the competitions condition.

## Problem to be solve
---
Based on the information provided in section 1.2, we can identify the main problems we need to address. These problems are listed in the table. For the first part of the project, we will focus more on the issues from 1 to 3. Our main objective is to learn and familiarize ourselves with the old TRUAV to understand the design decisions, electrical layouts, and other important aspects. This will help us to identify the areas that need improvement and propose manufacturing improvements to optimize the aircraft's weight. We will also conduct tests and evaluate the flight time of the TRUAV aircraft in copter mode and with the rotating tilt mechanism in cruise mode.

|No.|Issues|
|---|---|
|1|Gain an understanding of the basic principles and controls of tilt rotors.|
|2|Test and evaluate the flight time of the TRUAV aircraft in copter mode and with the rotating tilt mechanism in cruise mode.|
|3|Evaluate the structure of the TRUAV aircraft and propose manufacturing improvements to optimize its weight.|
|4|Conduct an analysis of the water resistance capabilities of the TRUAV aircraft and design appropriate measures to improve it.|
|5|Gain knowledge, analyze, and evaluate the operational conditions of the TRUAV aircraft in low-temperature environments.|
|6|Learn the theoretical foundations and design methods to give preliminary design parameters and 3D drawings of the TRUAV aircraft based on the old design.|
|7|Learn the theoretical basics to design and improve the aircraft structure suitable for the new mission.|
|8|Learn and compare the stability between the old and new designs of the TRUAV aircraft.|
|9|Test and evaluate the flight time and performance of the new design of the TRUAV aircraft in copter mode and with the rotating tilt mechanism in cruise mode.|

In the second part of the project, we will focus on issues 4 to 9. We will address several issues, including water resistance capabilities, operational conditions in low-temperature environments, theoretical foundations, design methods, and stability. By conducting these issues, we will be able to propose manufacturing improvements to optimize the aircraft's weight and ensure that it can operate effectively in heavy weather condition.

## Team member role
---
![](https://i.imgur.com/EuV9hHg.png)

