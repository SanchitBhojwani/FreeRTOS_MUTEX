# FreeRTOS Mutex Example on STM32 Blue Pill

## Overview

This project demonstrates the use of **Mutex in FreeRTOS** on the STM32 Blue Pill (STM32F103C8T6) using STM32CubeIDE and CMSIS-RTOS v2 API.

Three FreeRTOS tasks attempt to access shared GPIO resources. A mutex is used to ensure that only one task can access the critical section at a time, preventing simultaneous resource access and synchronization issues.

---

## Features

* FreeRTOS task scheduling
* Mutex synchronization
* Shared resource protection
* GPIO control using STM32 HAL
* CMSIS-RTOS v2 API
* Multi-tasking on STM32

---

## Hardware Used

* STM32F103C8T6 (Blue Pill)
* STM32CubeIDE
* FreeRTOS
* STM32 HAL Drivers

---

## RTOS Concepts Covered

* Task creation
* Task priorities
* Scheduler initialization
* Mutex creation and usage
* Critical section protection
* Resource synchronization

---

## Working Principle

Three separate FreeRTOS tasks toggle:

* PC13
* PC14
* PC15

Before accessing the GPIO section, each task acquires the mutex:

```c id="f4bgjq"
osMutexAcquire(myMutex01Handle, osWaitForever);
```

After completing execution, the task releases the mutex:

```c id="fw1v78"
osMutexRelease(myMutex01Handle);
```

This ensures that only one task accesses the shared section at a time.

---

## Project Structure

* `Task01` → Controls GPIO PC13
* `Task02` → Controls GPIO PC14
* `Task03` → Controls GPIO PC15

All tasks use the same mutex object:

```c id="i0azd0"
myMutex01Handle
```

---

## Concepts Demonstrated

* Mutual Exclusion
* Shared Resource Protection
* RTOS Synchronization
* Concurrent Task Management
* Embedded Multi-threading

---

## Future Improvements

* Add UART debugging output
* Use queues for task communication
* Add binary semaphore examples
* Add counting semaphore examples
* Implement interrupt-based synchronization

---

## Author

Sanchit Bhojwani
B.Tech Electronics and Communication Engineering (ECE)
Embedded Systems and Robotics Enthusiast


