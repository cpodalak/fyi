---
slug: is-industry-regressing-with-autosar
title: Is Industry Regessing with AUTOSAR?
tags: [autosar-big-picture]
---
# Is industry regressing with AUTOSAR?

## Story of AUTOSAR
### Motivation
Roughly two decades ago, the automotive industry operated with proprietary software development, hardware dependency, a lack of standards, and diverse interfaces. Basic software modules were tailored to specific electronic control units (ECUs).

The frequent obsolescence of microcontrollers before series production often led to last-minute software adjustments under tight time constraints. Integrating such diverse subsystems into a complex, interconnected vehicle network was error-prone and demanded extensive testing.

It may be hard for younger readers to imagine, but this was the situation that gave rise to the concept of AUTOSAR.

so, in early 2002, the concept for an open system architecture emerged in BMW’s electronics division.

## Release of Classic AUTOSAR
The Classic Platform Release 1.0 was published in June 2005 as the first release of the classic platform specifications.

The idea was to get rid of the late and risky adaptations of basic software for ECUs and to reduce the demand of internal and external resources involved in these software adaptations.

It envisioned moving towards open system architectures by creating a hardware abstraction layer (HAL), a standardized basic software stack, and a middleware layer with standardized interfaces to the applications.

It took a minimum of 10 years for some companies to accept, implement and transition AUTOSAR.

## Release of Adaptive AUTOSAR
Vehicles are evolving into cyber-physical systems, connecting to the internet, and becoming part of the Internet of Things (IoT). In addition, the industry moved towards realizing the vision of autonomous driving through advanced driver assistance systems and autonomous parking.

These new functions placed demands on hardware and software infrastructure, including high-end processors, hypervisor technology, communication with backend systems, and a focus on dependability, functional safety, and cybersecurity within the software architecture.

**In 2015, AUTOSAR released the Adaptive Platform to address new challenges posed by connected, automated, shared, and electrified driving (CASE).**

## 2020s
The car industry is changing like never before in its 150-year history. Cars are now filled with digital features and new business models. Car makers are trying new things and facing new competition.

Everyone in the industry now knows that software is crucial for cars, and most car makers are aiming high.

Past 20 years, AUTOSAR has created a comprehensive way to design software deeply embedded in cars. The classic platform still plays a role in driving sensors and actuators, while the Adaptive Platform is used in central ECUs. This means that cars are evolving into IT-edge devices, connecting to the cloud. Combining AUTOSAR with other technologies has the potential to establish a new software platform for vehicles but the drawbacks still exist though.

## Twist in the plot
**New players from the tech world have entered the car industry, bringing fast development and collaboration methods.**

This helps them deal with the complexity of automotive software, but the industry still needs to consider safety and real-time standards.

The key to future success is fast collaboration and open-source development in addition to existing safety-related methods.

As I mentioned before, main drivers for the increased complexity in our systems are the following four, which today are also often summarized by the acronym CASE:

**Connectivity:** Standardized communication protocols are needed to enable connectivity between vehicle ECUs and the external world.

**Autonomy:** The advancement of automated and autonomous driving necessitates high computing performance in today’s and future microprocessors (µPs), leading to new E/E architectures and centralized E/E architectures. This also sets new standards for security updates and promotes the use of non-automotive IT standards available as open-source software solutions.

Safety requirements for autonomous features demand traceable requirement specifications in addition to open-source software approaches.

**Sharing:** The abundance of software in future automotive systems requires applications from various sources and the reuse of non-differentiating commodity software, making a standardized Vehicle-Operating-System (Vehicle-OS) crucial to meet this demand.

**Electrification:** The introduction of electric vehicles brings about less complex electrified powertrains, making it easier for new players (OEMs) to enter the market.

This supports the reuse of commodity functions and encourages open-source solutions for Vehicle-OS.

## Future
Many automotive manufacturers are working to build their own vehicle operating systems, and there is a growing need for an ecosystem that simplifies access to both off-board and on-board systems.

Another emerging trend is the shift towards centralized computing platforms, eliminating the necessity for a separate microcontroller for each vehicle function.

There are already open-source standards and solutions for various industry needs, and it may not be necessary to adhere to a single standard like AUTOSAR. It’s possible to have multiple standards tailored to specific needs with/without/around AUTOSAR.

Volvo has developed a concept car using Rust. Zephyr is a scalable real-time operating system supporting various hardware architectures, designed for resource-constrained devices with a focus on security. SAFERTOS® is another option, based on the FreeRTOS kernel model and pre-certified to ISO 26262 ASIL D. Middleware protocols like DDS and API standards for data-centric connectivity are also available.

Combining alternatives along with AUTOSAR in use, vehicle manufacturers are developing their own Vehicle-OS with standards wrapped around open sources.

This could lead to a diverse range of ecosystems and interfaces, reminiscent of the situation 20 years ago but on a larger and more complex scale.

In order to get this under control, industry should focus on providing lighter alternatives to AUTOSAR with approved common services and protocols with a forward-looking approach. Additionally, industry needs a coordinated collaboration across different standardization and Open-Source Software organizations to continuously develop the common infrastructure.

## References

[News & Events AUTOSAR](https://www.autosar.org/news-events)

[Why Volvo thinks you should have Rust in your car?](https://medium.com/volvo-cars-engineering/why-volvo-thinks-you-should-have-rust-in-your-car-4320bd639e09)

[What is DDS?](https://www.dds-foundation.org/what-is-dds-3/)

[Zephyr Project](https://github.com/zephyrproject-rtos)