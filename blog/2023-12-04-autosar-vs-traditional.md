---
slug: AUTOSAR-vs-traditional-embedded-practices
title: AUTOSAR vs traditional practices
tags: [autosar-big-picture]
---
# AUTOSAR vs traditional embedded practices

Embedded system development, especially in the realm of automotive technology, can be approached through different methodologies. Among these, **AUTOSAR** (AUTomotive Open System ARchitecture) stands out as a dedicated framework tailored to address the intricate and safety-critical nature of automotive systems.

Now, before we dive into the specifics of the AUTOSAR methodology, let’s take a moment to explore some of the more traditional or widely-used strategies for crafting an embedded system.

## Regular embedded system development techniques
Traditional or regular embedded systems are less standardized and more diverse.

**Bare-Metal Programming**

In this methodology, **developers write code that runs directly on the hardware without an operating system**. It’s often used for simple or resource-constrained devices where maximum performance and minimum overhead are required.

Development is highly hardware-specific, with direct manipulation of registers and use of interrupts for task management.

Actuators for specific functions like mirror adjustment, seat position, or window control can be implemented with bare-metal programming, as these tasks usually require simple, deterministic control loops.

**RTOS-Based Development**

Real-Time Operating Systems (RTOS) are used when deterministic behavior and timing are crucial. The RTOS abstracts some of the hardware details, but developers still need to have a good understanding of the system’s timing and resource constraints.

Examples include FreeRTOS, VxWorks, and QNX, which provide a framework for task scheduling, inter-task communication, and timing services.

**Linux-Based Development**

For more complex systems that require networking, file systems, or high-level application frameworks, a full-fledged operating system like Linux might be used.

Linux offers a rich set of features and is supported by a wide variety of processor architectures.

Development can leverage standard programming languages and open-source tools, but may still require customization of the Linux kernel or device drivers.

**Proprietary or In-House Frameworks**

Some organizations develop their own proprietary frameworks or libraries tailored to their specific hardware and application requirements. These frameworks can range from simple hardware abstraction layers to complex software ecosystems.

They may offer advantages in terms of performance or integration with company-specific technology but can also lead to increased maintenance and portability challenges.

**Model-Based Development (MBD)**

MBD uses high-level modeling tools like MATLAB/Simulink to design the system, which can then automatically generate code for various hardware targets. This approach is useful for complex control systems and signal processing applications.

**Vendor-Specific Ecosystems**

Many microcontroller and processor vendors provide integrated development environments (IDEs), software libraries, and tools specific to their hardware. These ecosystems simplify development for the vendor’s hardware but can lock you into using that vendor’s products.

Some examples are Microchip’s MPLAB X, Texas Instruments’ Code Composer Studio, and STMicroelectronics’ STM32Cube.

## AUTOSAR Methodology
AUTOSAR provides a standardized architecture for automotive software development. It aims to improve software reusability, scalability, and interoperability between different vehicle components and vehicle manufactures.

The AUTOSAR methodology roughly describes the concept of ECU (Electronic Control Unit) development by the basic work product flow from a global view.

**Example**: Temperature Control System
Let’s dive a bit deeper by comparing AUTOSAR methodology with regular embedded system development using an example of developing a temperature control system.

A temperature control system typically consists of several key components that work together to regulate temperature within a desired range. The exact configuration can vary depending on the complexity of the system and the specific application, but here are the fundamental components you would generally find

  - Sensor(s) — To measure current temperature.
  - Controller — The brain of the system which processes input from sensors and determines output to heating or cooling devices.
  - Actuator(s) — Heating or cooling elements.
  - User Interface — Allows user to set desired temperatures.
  - Regular Embedded System Development approach
  - Requirements Analysis : Determine the functional requirements, such as the desired temperature range and response time.

**Hardware Selection:**  
Next, you pick out a microcontroller that’s got enough oomph to run your code and a sensor that’s accurate enough so you don’t end up sweating or freezing.

**Software Design:**  
Now you sketch out how your code’s going to work. You’ll need some loops to check the temperature, some logic to decide when to turn on the heat, and a way for people to adjust the settings.

**Implementation:**  
Time to get coding. You roll up your sleeves and start writing lines of C or C++ that tell the microcontroller what to do.

**Integration and Testing:**  
You’ve got to make sure your code plays nice with the hardware. Integrate the software with the hardware and test the system to ensure that it meets the requirements.

**Maintenance:**  
After everything’s up and running, you’re not done yet. If a bug pops up or you want to add new features, you get back in there and update your code.

Now if you want to add touch screen, there is high chance of touching almost all modules because you never thought to standardize your interfaces.

## AUTOSAR Approach
Think of AUTOSAR like a big LEGO kit for car software. It’s got all these standardized blocks you can snap together to build software for cars.

It’s all about making sure the pieces you create can be used in different cars and play nicely with parts from other car makers.

Now, let’s see how we’d whip up a temperature control system with this toolkit.

**Requirements Analysis:**  
Just like when you’re planning any project, you gotta figure out what you need. In the car world, there are some extra rules to follow, like making sure everything is super safe because, well, it’s a car.. For example, ISO 26262 for functional safety.

**Software Architecture:**  
AUTOSAR sets up a neat structure for your code with different blocks.

You’ve got the Application Layer where your temperature control magic happens, the Runtime Environment (RTE) that’s like a middleman passing messages, and then the layers that talk to the actual car hardware.

**Component Design:**  
Now, you get to create the bits and pieces of the software that control the temperature.

The best part is that you can use them over and over in different areas. Just like libraries.

You describe these pieces with a fancy instruction manual called ARXML.

**Configuration:**  
You’ve got your pieces ready, but you need to set them up for your specific ride. That’s like tuning your sound system to get the perfect bass.

You use some special AUTOSAR tools to make sure all the software bits are working together properly.

**Integration and Testing:**  
It’s time to put your creation into action and make sure it doesn’t go haywire.

More of like connecting blocks.

You’ll run it through some virtual tests on your computer (that’s SIL) and then with real car parts (that’s HIL) to catch any gremlins before they cause trouble.

**Maintenance:**  
Since you’ve used these standardized LEGO-like pieces, when it’s time to update or fix something, it’s way easier.

You can just swap out the old piece for a new one, and you’re good to go.

So, there you have it. Using AUTOSAR is a bit like having a guidebook that makes sure everyone’s building their temperature control systems with the same set of rules, which is pretty handy when you’re making something as complex as a car.

## Key takeaways with a different example for better visualization

**Standardization:**  
Like I mentioned, With AUTOSAR, it’s like everyone’s using the same cookbook, which makes it easier to share recipes and tools.

In regular embedded development, each chef might have their own secret recipes and special kitchen setup.

**Abstraction:**  
AUTOSAR is like having smart kitchen appliances that adjust themselves to the recipe.

In regular development, the chef has to fiddle with the knobs and settings for each dish.

**Interoperability:**  
AUTOSAR’s like a potluck where everyone brings dishes made using the same cookbook, ensuring all the food goes well together.

Regular development is more like everyone bringing a dish without knowing what the others are making, which can lead to a mismatched meal.

**Tooling:**  
Working with AUTOSAR might mean you need some pricey, high-tech kitchen gadgets that take time to learn how to use.

For regular embedded development, you might get by with more basic tools, or even DIY some gadgets to suit your needs.

**Scalability:**  
AUTOSAR’s like having a cookbook that covers everything from making toast to preparing a five-course meal. It can handle recipes for all sorts of occasions.

In traditional embedded development, you might need a new cookbook — or even a new kitchen — every time the scale of your cooking changes.

**Not everyone grasps AUTOSAR as originally intended, and since the AUTOSAR methodology doesn’t clearly define roles and responsibilities. Whereas, company-specific processes and vendor tools tend to complicate it further.**
