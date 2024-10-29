# Second sequence diagram: Calling the function

For the second sequence diagram, I will demonstrate how my tasks call specific functions to complete the process. For example, when having breakfast, I need to call a function "Prepare breakfast",heading to the university, I call functions like "Wait for the elevator" 


```plantuml
skinparam backgroundColor transparent
@startuml
participant User as U
participant Kitchen
participant Breakfast
participant Elevator

U -> Kitchen : Go to the kitchen
Kitchen -> Breakfast : Call prepare breakfast function
Breakfast -> Kitchen : Toasts with eggs and tea ready

U -> Breakfast : Eat breakfast
U -> Elevator : Go to the elevator
Elevator -> Elevator : Call wait for elevator function
Elevator -> U : Enter the elevator
@enduml
```