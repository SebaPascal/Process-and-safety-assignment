# Second state diagram: Going to university

The second task represents my routine after finishing breakfast and heading to the university. This state diagram outlines the process by taking the elevator, and then walking to the university.

```plantuml
@startuml
[*] --> Elevator : Proceed to elevator

state Elevator {
    [*] --> CallElevator : Press button, wait for elevator
    CallElevator --> EnterElevator : Enter on arrival, select floor
    EnterElevator --> ArriveGroundFloor : Descend to ground floor
    ArriveGroundFloor --> ExitElevator : Leave elevator
}

state WalkToUniversity {
    [*] --> ExitBuilding : Head towards building exit
    ExitBuilding --> StartWalk : Determine path to university
    StartWalk --> WalkToCampus : Proceed along path (Duration: 3-5 min)
    WalkToCampus --> EnterUniversity : Reach university entrance
    EnterUniversity --> NavigateToClassroom : Head to designated classroom
}

Elevator --> WalkToUniversity : Exit elevator
WalkToUniversity --> [*] : Arrive at classroom
@enduml

```
