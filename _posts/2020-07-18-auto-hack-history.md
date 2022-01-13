---
title: Brief history of automotive hacking
date: 2020-07-18T18:48:00-00:00
categories:
  - blog
tags:
  - auto
  - infosec
---

As part of my thesis on automotive hacking I reviewed a lot of literature and tried to piece together the history of this subject, leading to producing a 'Brief history of automotive hacking' - first in the form of a [Twitter thread][20], now here.

Vehicle hacking began almost as soon as ECUs entered the mainstream auto industry in the 1980s, with car enthusiasts seeking to tune their vehicles by modifying the ECU firmware. It took 30 years until the first comprehensive research into vehicle security was [published][1] in 2010, by Koscher and Checkoway et al. Prior to this study, other academic research in this field was largely theoretical. The 2010 study demonstrated practically on two cars the security flaws which still exist today and form the basis of many automotive attacks. These attacks focus on firmware modification and CAN message injection, both requiring reverse engineering. 

Despite the 2010 paper featuring sophisticated attacks, the researchers required physical access to the vehicle, and so the attacks could be matched for example, by cutting the brake wires. However, just a year later in 2011, Koscher and Checkoway et al. released their follow on [paper][2], demonstrating remote attacks on the same vehicles. This significant paper exposed remote vulnerabilities in the information entertainment (infotainment) system, Bluetooth stack and Telematics unit. The researchers exploited these remote entry points, leading to compromising the CAN bus and performing CAN bus message injection. This paper proved provided a serious wake-up call to the automotive over security leading to some companies taking note while others not so much.

Fast forward a year to 2012 and DARPA funded two hackers inspired by the previous work of Koscher, Checkoway et al., with the goal to release open-source hacking tools to inspire more research into this area. The two researchers, Miller and Valasek, released their first [investigation][3] with example attacks on a 2010 Ford Escape and a 2010 Toyota Prius. These attacks were based on physical access to the vehicle and once again showed the great ease of CAN bus injection and firmware modification. Proving a success, DARPA then followed with another grant in 2013 for Miller & Valasek, this time to produce a [platform][4] that would help researchers conduct automotive security research without having to purchase a vehicle. Now inspired to turn the attacks from physical to remote, Miller & Valasek began [analysing][5] remote attack surfaces of 21 vehicles. They identified the 2014 Jeep Cherokee as the most vulnerable and continued to research this vehicle culminating in perhaps the most publicised [remote hack][6] of a vehicle. In this attack, Miller & Valasek demonstrated their hack live on a willing journalist driving a Jeep Cherokee on a highway; controlling the speakers, window-wipers, dashboard and finally killing the engine. This sophisticated attack was the culmination of their 3 years of research, leading to an attack chain exploiting vulnerabilities in the vehicles remote networking, infotainment architecture and poorly designed CAN bus gateways. 

The Jeep Hack, like the Koscher 2011 paper, inspired another wave of researchers to get involved in vehicle hacking and these researchers were also now armed with the introduction of the '[bible][7]' of vehicle hacking, authored by Craig Smith the founder of Open Garages a vehicle tuning enthusiast group.

Next came DEFCON 23 in 2015, the renowned hacker conference, where much research was presented on the topic, and the Car Hacking village (CHV) was formed. The CHV featured a CTF with physical cars and components to hack. Two main presentations stood out, one by Samy Kamkar and another by Marc Rogers and Keven Mahaffey. Kamkar's [presentation][8] revealed vulnerabilities in the General Motors car app OnStart leading to remotely turn on/off the engine, horns and locate the vehicle. Kamkar also presented rolling code key relay attacks for car key entry. Rogers and Mahaffey's [presentation][9] revealed the first major investigation into Tesla vehicle security, resulting in the ability to access and remotely control the infotainment system.

Also in 2015, well-known hacker George Hotz started the company Comma AI which now commercially sells autopilot hardware to attach onto cars. This [hardware hack][10] can control the steering and speed through CAN message injection accessed by the OBD-II diagnostics port. With vehicle hacking becoming more prominent Tencent Keen Security Research Lab formed in 2016, who have since released [Tesla vulnerabilities][11] every year and more recently [BMW][12]. The vulnerabilities KeenLab have exploited range from hacking the Tesla infotainment console through a WebKit [vulnerability][13] to [fooling Tesla autopilot][14] with adversarial examples.

Since 2016, the field has grown greatly with the number of researchers, penetration testing companies and security engineers in this line of work continually growing. Independent researchers have been encouraged by companies offering bug bounty programs such as [Fiat-Chrysler][15], [Tesla][16] and [Ford][17]. Penetration consulting companies such as Pen Test Partners have released [blog posts][18] of their experience so far in this field and there's a constant stream of automotive security roles being advertised. Looking towards the future, vehicles will remain an interesting target to hack, mainly due to the inherent complex vehicle networks but also due to vehicles containing many third-party systems.

To read more, there's a good [github repo][19] with a load of resources I incidentally found after I had researched most of the above.

[1]: <http://feihu.eng.ua.edu/NSF_CPS/year1/w9_1.pdf> "Experimental Security Analysis of a Modern Automobile" 

[2]: <https://www.usenix.org/legacy/event/sec11/tech/full_papers/Checkoway.pdf> "Comprehensive Experimental Analyses of Automotive Attack Surfaces"

[3]: <http://illmatics.com/car_hacking.pdf> "Adventures in Autmotive Networks and Control Units"

[4]: <http://illmatics.com/car_hacking_poories.pdf> "Car Hacking: For Poories"

[5]: <http://illmatics.com/Remote%20Car%20Hacking.pdf> "A Survey of Remote Automotive Attack Surfaces"

[6]: <https://www.wired.com/2015/07/hackers-remotely-kill-jeep-highway/> "Hackers Remotely Kill a Jeep on the Highway—With Me in It"

[7]: <http://opengarages.org/handbook/ebook/> "THE CAR HACKER’S HANDBOOK: A Guide for the Penetration Tester"

[8]: <https://www.youtube.com/watch?v=UNgvShN4USU> "Drive it like you Hacked it: New Attacks and Tools to Wireless"

[9]: <https://www.youtube.com/watch?v=KX_0c9R4Fng> "How to Hack a Tesla Model S"

[10]: <https://medium.com/@comma_ai/a-panda-and-a-cabana-how-to-get-started-car-hacking-with-comma-ai-b5e46fae8646> "How to get started car hacking with comma.ai"

[11]: <https://keenlab.tencent.com/en/whitepapers/Experimental_Security_Research_of_Tesla_Autopilot.pdf> "Experimental Security Research of Tesla Autopilot" 

[12]: <https://pdfs.semanticscholar.org/deab/31489a1d35c6518c50bf8f617dde855.pdf> "0-days & Mitigations: Roadways to Exploit and Secure Connected BMW Cars"

[13]: <https://www.blackhat.com/docs/us-17/thursday/us-17-Nie-Free-Fall-Hacking-Tesla-From-Wireless-To-CAN-Bus.pdf> "WebKit Vulnerability by Keen Security Lab"

[14]: <https://keenlab.tencent.com/en/2019/03/29/Tencent-Keen-Security-Lab-Experimental-Security-Research-of-Tesla-Autopilot/> "Tencent Keen Security Lab Experimental Security Research of Tesla Autopilot"

[15]: <https://bugcrowd.com/fca> "Fiat-Chrysler Automotive bug bounty program"

[16]: <https://bugcrowd.com/tesla> "Tesla bug bounty program"

[17]: <https://hackerone.com/ford?type=team> "Ford bug bounty program"

[18]: <https://www.pentestpartners.com/automotive-security/> "PTP automotive"

[19]: <https://github.com/jaredthecoder/awesome-vehicle-security> "Auto hack repo"

[20]: <https://twitter.com/wmvndrscht/status/1226163392198664193?s=20> "My twitter thread"
