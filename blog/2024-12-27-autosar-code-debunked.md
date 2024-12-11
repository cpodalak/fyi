---
slug: autosar-code-debunked
title: AUTOSAR application code debunked
tags: [autosar, C]
---

# AUTOSAR application code debunked

This article aims to provide a comprehensive understanding of AUTOSAR (AUTomotive Open System ARchitecture) through a practical example. We will develop a simple obstacle detection program, breaking it down from a monolithic C program into a modular design that mirrors AUTOSAR's approach. Finally, we will delve into system design, network topology, and communication, illustrating these concepts with ARXML snippets.

We will walkthrough this evolution of simple program in phases

  1. Setup Example - Obstacle detection program
  2. Refactor monolithic program to Functions
  3. Seperate functionalities into modules
  4. Real-car analogy
  6. Write ARXMl for same example
  5. Refactor modules to autosar format
  6. Conclusion

## Phase 1: Setup Example
Simple Obstacle Detection Program
The initial step involves creating a straightforward C program that encompasses all functionalities within the main function. This program reads sensor data and actuates a motor to stop when an obstacle is detected.

```C

#include <stdio.h>
#include <stdbool.h>

int main() {
    bool obstacleDetected = false;
    int sensorData = 0;

    printf("Reading sensor data...\n");
    // Simulate reading sensor data
    sensorData = 10; // Assume 10 is the threshold for detecting an obstacle

    if (sensorData >= 10) {
        obstacleDetected = true;
    }

    if (obstacleDetected) {
        printf("Obstacle detected! Stopping motor...\n");
        // Code to stop the motor
    }

    return 0;
}
```

## Phase 2: Functions
We refactor the initial program by breaking down the logic into separate functions. This enhances readability and maintainability.

```C

#include <stdio.h>
#include <stdbool.h>

bool readSensorData(int *sensorData) {
    *sensorData = 10; // Simulate reading sensor data
    return *sensorData >= 10; // Returns true if obstacle is detected
}

void stopMotor() {
    printf("Stopping motor...\n");
    // Code to stop the motor
}

int main() {
    int sensorData = 0;
    bool obstacleDetected = readSensorData(&sensorData);

    if (obstacleDetected) {
        stopMotor();
    }

    return 0;
}

```

IN PROGRESS

