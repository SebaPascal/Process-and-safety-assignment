# First sequence diagram: Comunication between tasks

For the first sequence diagram, I will explain the interactions between my tasks. For instance, after finishing breakfast, I immediately start preparing my things for the university. This diagram will illustrate how these tasks communicate and transition from one to the next.

```plantuml
@startuml
actor Me as Operator
participant GVL
participant TaskBreakfast
participant TaskElevator

Operator -> TaskBreakfast : Start Task
TaskBreakfast -> GVL : Check Hungry
alt Hunger TRUE
    TaskBreakfast -> TaskBreakfast : Prepare my breakfast()
    TaskBreakfast -> GVL : Set Breakfast Ready = TRUE
else Hunger FALSE
    TaskBreakfast -> GVL : Set Breakfast ready = FALSE
end

TaskBreakfast -> TaskElevator : Notify Breakfast Complete
TaskElevator -> GVL : Check Breakfast Ready
TaskElevator -> TaskElevator : Initiate Elevator Process
TaskElevator -> GVL : Set bEnElevador = TRUE
TaskElevator -> Operator : Task Complete

@enduml
```