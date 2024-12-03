# Ideas

- [50KM Bluetooth Range & 2Mbps Speed: MultiNav Pro+ BLE by RFOXiA — Kickstarter](https://www.kickstarter.com/projects/rfoxia/50km-bluetooth-long-range-2-mbps-data-rate?ref=discovery_category&total_hits=54928&category_id=334)
- Digital construction visualization
- Embedded systems EDR/XDR/AV which runs at kernel level which can be dynamically loaded. Can use AI to detect intrusion of the device and harden memory allocations. Can detect brute force attacks, malware, and suspicious network traffic to send alerts to a controlled network. 
- AI-powered video analysis analyze real-time videos to recognise faces, license plates and even predict potential threats. [Detecting threats](https://link.springer.com/article/10.1007/s11042-021-10809-z)

# AI detection used on NVR/DVR systems

> What does it do? How does it work?

This system will be a controlled surveillance system. The NVR/DVR system will work normally all it will do differently is upload it's video footage using HVEC or JPEG (a low power and efficient format to pass video format over network). The cloud based system will be the brains behind the machine in the first stage. Within the cloud based system it will hold the neural network which will receive the data, process it and make predictions and analysis on the processed data. Any detections or data found which is abnormal, is sent to defined endpoints to alert the end user.

The NVR/DVR system will have states it goes through dependent on the configuration given by the defined endpoint. States:
- **CRITICAL**
	- *Description*: in this state the system operators at full capacity, with all detection modules activated (facial recognition, license plate recognition, motion detection, and infrared monitoring)
	- *Features*
		- Continuous, AI cloud interaction to the cloud based system
		- Real-time detection and critical alerts for faces, vehicles, motion and weapons
		- High power consumption due to active processing and cloud communication
		- Used in high-risk or high-security environments (e.g., bank, restricted areas)
- **ACTIVE**
	- *Description*: This state actively monitors, but not as intensive as the *CRITICAL*. some detection modules may be reduced or localized to save power. For example packets to the *Cloud based system* may have a bigger sleep time.
	- *Features*
		- Motion detection (can be altered in configuration once motion detected can switch to critical state)
		- Cloud interaction may still occur for advanced analytics, but at a reduced rate
		- Lower power consumption compared to *CRITICAL* but still functional for ongoing surveillance.
- **MONITORING**
	- *Description*: This state represents a standard non-intensive surveillance operation. The system continuously observes the environment without any immediate alerts or intensive processing ensuring basic monitoring. 
	- *Features*
		- Ongoing visual and motion detection at a reduced level of intensity.
		- Cloud communication for standard reporting and logging.
		- Reduced power consumption
		- Can be used for general surveillance in low-risk environments like office buildings or public spaces
- **PASSIVE** 
	- *Description*: The system is mostly idle but still capable of recording data or capturing events if trigged by specified parameters (e.g motion, sound). Minimal interaction with cloud or other components occurs in this state.
	- *Features*: 
		- Ongoing visual and motion detection at a reduced level of intensity.
		- Cloud communication for standard reporting and logging (not real-time or critical)
		- Very low power consumption
		- Suitable for environments where constant monitoring is unnecessary, such as during non-working hours or in low-security areas.
- **STANDBY** 
	- *Description*: The system is in a formant state, where most components are powered off or in a low-power mode. It remains ready to be activated quickly if needed but is not actively monitoring or processing data.
	- *Features*
		- All or most detection modules (facial recognition, motion detection, etc.) are turned off or in a low-power idle mode.
		- Cloud communication is dormant or highly limited.
		- Immediate activation possible when motion or other triggers occur.
		- Extremely low power consumption.
		- Used when surveillance is temporarily unnecessary or when there’s no imminent risk but the system should be ready for quick activation.
- **EMERGENCY** 
	- *Description*: A special state triggered by critical alarms or human intervention. The system activates at full capacity with prioritized focus on the specific emergency situation.
	- _Features_:
	    - All detection modules activate at maximum efficiency (e.g., instant facial recognition, license plate recognition, motion, and infrared monitoring).
	    - Priority cloud communication for real-time alerts, logs, and data sharing.
	    - Full power consumption to ensure no delays in detecting or responding to the emergency.
	    - Used in high-risk situations where immediate intervention is needed, such as armed intrusions or catastrophic events.

For crime detection we could implement infrared videoing to detect concealed weapons and alert the user endpoint.

Going into the future we can use IoT edge computing to allow AI to run locally, this will be later in the future when embedded processors are improved.

![NVR](https://github.com/Eren-Yeager7/AjarTech/raw/refs/heads/main/NVR_Concept.png)

> Explain the problem it addresses. How does it improve people's lives or make an existing process more efficient?

This addresses the problem of having a live end user monitoring the video footage, this can send alarm based or general alerts to a defined endpoint. Having AI make facial, license plate detection and predictions on footage can be very beneficial to a security company having to have a security guard monitor footage 24/7. Also the detection of weapons could be beneficial in a bank robbery, it could detect a robber or a potential robber using infrared detection and send that information to the police directly with the footage clip, so it doesn't danger staff member pressing an alert manually.

> Identify potential users. Who would find this technology most useful? Consider specific industries, age groups, or demographics

Potential users could be banks, government agencies, security facilities, small businesses and intel agencies. The potential users vary due to different states being efficient for a range of users. This type of technology may be most useful for high security agencies which need constant alerts, and monitoring or government intel agencies who need constant surveillance. The age groups and demographics again vary a lot, but the age groups who'd buy this type of product I'd think would be 20-50 age group and there isn't a particular demographic who would buy this.

# Exploration and Conceptualisation
> Research Futuristic Technologies: Explore current cutting-edge technologies and innovations that might be early indicators of future developments

Well a good future development would be having the processing of footage to be done on the actual hardware for example the ARM chip which is standard for most embedded devices have introduced the new **Armv9-A** architecture and it adds a lot of new features for doing *Machine Learning* directly on the chip with it's accelerated processing of large datasets without having to recompile software and remain power efficiency through improved memory usage. 
#### **Armv9-A chip**
![Armv9](https://github.com/Eren-Yeager7/AjarTech/raw/refs/heads/main/Armv9.png)

This allows for us in future development to handle everything locally instead of remotely, without having to give up efficiency.

> Challenges and Feasibility: Discuss potential obstacles, such as technical limitations, cost, ethical considerations, and regulatory hurdles.

Well this project would encounter a lot of obstacles, firstly we'd have to look into buying CPU design licenses from [HiSilicon]([HiSilicon - Wikipedia](https://en.wikipedia.org/wiki/HiSilicon)) which is owned by [Huawei]([Huawei - Wikipedia](https://en.wikipedia.org/wiki/Huawei)) a Chinese company which could bring up issues with government agencies. We'd have to buy their [SoCs]([System on a chip - Wikipedia](https://en.wikipedia.org/wiki/System_on_a_chip)) which currently do not support any Armv9-A Instruction set, but they do support Armv8-A Instruction Set. Making our own **SoC** would be unfeasible unless we raised a massive amount from share holders, and even then it seems unfeasible. So having to rely on a company especially a Chinese company could bring up issues.

The cost of development may be expensive because we'd need experienced embedded programmers which would be quite hard to find. An if we were to open a child company to handle **SoCs** designs we'd need a lot of experienced developers and hardware architects. This would be costly. 

Ethical considerations would be that if it's okay for intelligence agencies or government agencies to do mass surveillance and collect faces, and keep all that information. This could cause public outrage.
## Summary
This proposal focuses on developing an advanced AI-powered surveillance system for NVR/DVR (Network Video Recorder/Digital Video Recorder) systems, with cloud-based AI processing for real-time video analysis. The system aims to improve security by integrating various detection capabilities such as facial recognition, license plate recognition, motion detection, infrared monitoring for concealed weapons, and more. The surveillance system operates in multiple states (Critical, Active, Monitoring, Passive, Standby, and Emergency) that adjust the level of detection and power consumption based on the situation's urgency.

Key features:
- **Critical State**: Full AI detection capabilities and constant cloud interaction for high-risk areas.
- **Active State**: Less intensive processing with cloud-based AI interaction at a reduced rate, used for regular surveillance.
- **Monitoring State**: Basic surveillance with low power consumption, ideal for general areas.
- **Passive State**: Minimal activity, low power consumption, useful for non-critical periods.
- **Standby State**: Inactive but ready to activate when triggered.
- **Emergency State**: Full activation triggered by critical alarms or events.

The system would enhance security by reducing the need for constant human monitoring and can send alerts to relevant authorities when abnormal activity (e.g., weapons, unauthorized individuals) is detected. It could be especially useful for high-security environments such as banks, government buildings, and security agencies.

Future developments include leveraging **Edge Computing** and **IoT** for localized AI processing on embedded devices like **ARMv9-A** chips, which would enable more efficient, real-time, on-device analytics, removing the need for cloud reliance.

However, the proposal acknowledges several potential challenges:
1. **Technical limitations**: Developing or sourcing the necessary **SoCs** (System on a Chip), especially given potential geopolitical challenges with suppliers like HiSilicon.
2. **Cost**: High development costs for software, hardware, and experienced personnel.
3. **Ethical concerns**: Surveillance, especially with facial recognition, raises issues of privacy and the potential misuse of collected data.

## Conclusion

This AI-driven surveillance system represents a significant step toward automating and enhancing security processes across various industries, particularly in high-risk environments. By reducing human oversight and using AI to detect threats in real-time, it promises to improve both the speed and accuracy of response times to security incidents. However, the project faces substantial hurdles, particularly related to technology acquisition, development costs, and ethical concerns around privacy and surveillance. Moving forward, local processing on embedded devices, such as the **ARMv9-A** chip, could help mitigate some of these challenges, but careful consideration will be needed regarding the potential societal impacts of mass surveillance technologies.


