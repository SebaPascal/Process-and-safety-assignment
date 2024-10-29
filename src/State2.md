# Second state diagram: Going to university

The second task represents my routine after finishing breakfast and heading to the university. This state diagram outlines the process by taking the elevator, and then walking to the university.

```plantuml
@startuml
skinparam backgroundColor transparent
'skinparam linetype ortho'

[*] --> TakeElevator
TakeElevator -r-> FirstFloor : Eletor arrives to fourth floor
FirstFloor --> ExitBuilding : Walk to building entrance
ExitBuilding -l-> WalkToUniversity : Exit building
WalkToUniversity --> ArriveUniversity : Arrives at the university
ArriveUniversity -r-> WalkToClassroom : Walk to the classroom
WalkToClassroom --> [*]

@enduml
```
