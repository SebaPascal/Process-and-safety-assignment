# Second state diagram: Going to university

The second task represents my routine after finishing breakfast and heading to the university. This state diagram outlines the process by taking the elevator, and then walking to the university.

```plantuml
@startuml
[*] --> Elevator : Proceed to elevator

state Elevator {
    [*] --> CallElevator : Press button, wait for elevator
    CallElevator --> EnterElevator : Enter on arrival, select floor 1
    EnterElevator --> ArriveGroundFloor : Descend to ground floor
    ArriveGroundFloor --> ExitElevator : Leave elevator
}

state WalkToUniversity {
    [*] --> ExitBuilding : Head towards building exit
    ExitBuilding --> StartWalk : think of the path to university
    StartWalk --> WalkToCampus : Proceed along path
    WalkToCampus --> EnterUniversity : Reach university entrance
    EnterUniversity --> WalkToClassroom : Head to designated classroom
}

Elevator --> WalkToUniversity : Exit elevator
WalkToUniversity --> [*] : Arrive at classroom
@enduml
```
