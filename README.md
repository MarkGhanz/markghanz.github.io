# About Beitong (Betop) Kunpeng 70 (BTP-KP70B)
Got an Beitong Kunpeng 70 to test.   
## A/B Difference
I found it like its younger brother KP40 has an A/B hardware difference for CN and Intl units. The one on minixpc was BTP-KP70A, same as on JD, initially, and it was changed to KP70-B. Every KP70 on Aliexpress is BTP-KP70B. The "A" uses NearLink and polls at 2000Hz maximum and "B" uses Beitong's proprietary 1000Hz 2.4G while its dongle shows up as `20bc:5160` Shenzhen ShanWan blah blah blah as revealed by `lsusb` on Linux if successfully connected but before claimed by other kernel gamepad drivers. The Linux on my machine was Arch Linux with 6.18.0 kernel. In addition, the only data available on gamepadla showed firmware version 1.1.9. However, the latest firmware for the "B" variant from their true English software was 1.0.3 for both controller and the dongle. So it proved that user on gamepadla imported an "A" variant and nobody online including me knows what are the real sticks latency and button latency for the "B" variant. I cannot afford to tear the controller apart to test it using P82. The dongle itself unconnected had `20dd:5160` as USB VID:PID. I was not saying either A or B is superior to the other as the AI functionalities on "A" according to bilibili testers were more of gimmicks with quirks. My chat with their customer service didn't reveal any difference besides the wireless transmission and AI.   
## Weird Intentional behavior on Linux
And finally, the ONE OF A KIND behavior across probably any 3rd party non-for-switch gamepads.   
Most of you may know these Chinese gamepads are using Xinput via dongle on Windows and their dongles are recognized as Xbox 360 controller under Linux if it is functional. There are some cases that the gamepad shows up but not functional like in the case of ZD Ultimate Legend whose dongle impersonated Xbox 360 controller but inputs cannot be recognized. The switch mode is usually reserved for bluetooth and wired for actual switch usage, with a polling rate about 125Hz or ~250Hz.   
That's WILDLY DIFFERENT from BTP-KP70B.   
When connected via its dongle, it was shortly picked up by hid-nintendo, no matter if joycond was active, and recognized as A NINTENDO SWITCH PRO CONTROLLER.   
Hardwaretester HTML cannot detect it, but for literally everything else, it can be detected. The joysticks was a bit off in steam, but I used it on ZZZ without steam input kicking in and the buttons, joysticks, triggers functions fine as a "Nintendo Switch Pro Controller" with the usual A/B button swap. Both steam and a yuzu fork instantly recognized ITS GYRO with nothing needed on the controller side. No drifting if stationary. Only missing rumble.   
Since then my mind was blown. I've used Flydigi Apex 4, ZD Ultimate Legend, and Bigbigwon Rainbow 3. Their dongles are all picked up by xpad and may or may not work as a Xbox360 controller. But recognized as a Nintendo Switch Pro Controller? Without tweaks and just PnP? Working gyro just missing rumble?   
## Customer service talking gibberish
That gave me loads of suspicion about them "not support" Linux as shown from the following excerpt of a chat between me and their customer service.   
If Beitong really did absolutely nothing regarding Linux, then the controller should be a finicky Xbox360 Controller via its dongle.   
If it is a Nintendo Switch Pro Controller with just ONE STEP from fully featured instead, then I think the odds of Beitong did it deliberately is >99%.  
I feel like I am telling a horror story. But anyway, if anybody has the "A" variant, please test its behavior under Linux if you have time to complement my findings.  
## Follow up: Engineering Nonsense
Alright, this is where the true engineering nonsense introduces itself. 
Let's first forgot its manual hosted on their website is splitted into [KP70-1](https://game.cdn.betophall.com/data/video/fun/user%20manual-KP70%20elite%20game%20controller%20ver.1.pdf) and [KP70-2](https://game.cdn.betophall.com/data/video/fun/user%20manual-KP70%20elite%20game%20controller%20ver.2.pdf), and each of them is close to 160MB, with just one poster and one page. I suspect the only reason why they split the manual in this way is probably they made their printer out of memory.  
Next, out of curiosity, I used gamepadla's python script to test the dongle's polling rate after it's claimed by `hid-nintendo`.  
And the result...was around 71Hz.  
71Hz.  
It's not only substantially lower than even Switch Pro's 125Hz, but also does not match any reasonable polling rate given 1ms USB frame at 12Mbps.  
PS3 controller polls at 62.5Hz, but that is 1000/16, and definitely have reasonable engineering considerations behind it.  
71Hz is even a rounded number.  
An around 14ms polling period is in what way reasonable? It can be 8ms, 4ms, 2ms, 1ms, or combining multiple packet in one 1ms frame. It just CANNOT be around 14ms.  
On gamepadla, KP70-A's wireless sticks latency seems also be around 14ms.  
So I am pretty sure that this is 100% intentional, intentional malice.
## Conclusion
I decided to setup an endowment. Beitong KP70 and 71Hz endowment.  
No funding. No honor. Just an endowment for the true anti-excellence.  
