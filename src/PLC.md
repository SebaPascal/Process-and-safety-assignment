# PLC Program

## GVL

This section contains my Global Variable List (GVL), where I defined the shared variables accessible across different tasks in the program.

![GVL](/images/GVL.png)

## First Task

The first task manages the initial processes in the program flow. It reads and updates specific variables from the GVL, depending on states and timers. This task represents the process of me feeling hungry and heading to the kitchen. Once there, three timers (TON) begin counting, representing the preparation of my food. When these timers finish, the task progresses to the eating stage, followed by heading to the elevator, which triggers the start of the second task.

![Breakfast](/images/BreakfastPRG.png)

## Second task

The second task is another independent process running in parallel with the first. In this code, after reaching the first floor, I need to check whether I have classes. If I have no classes, the task adjusts, directing me to go to the gym instead

![Elevator](/images/ElevatorPRG.png)

## Function called

This section describes a simple function called by the elevator task. The function, triggered by a global variable "check_class", activates upon reaching the first floor. If classes are scheduled, the function sets an output to true, guiding me to class; otherwise, it returns false, directing me to head to the gym.

![Function](/images/Function.png)