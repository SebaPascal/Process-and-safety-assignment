# Second sequence diagram: Calling the function

For the second sequence diagram, I will demonstrate how my tasks call specific functions to complete the process. For example, when having breakfast, I need to call a function "Prepare breakfast",heading to the university, I call functions like "Wait for the elevator" 


```plantuml
@startuml
actor Me
participant TaskBreakfast
participant PrepareBreakfast as FunctionBreakfast
participant TaskElevator

Me -> TaskBreakfast : Start Task
TaskBreakfast -> FunctionBreakfast : Prepare Breakfast(Hungry)
alt Hunger TRUE
    FunctionBreakfast -> TaskBreakfast : Return Breakfast ready = TRUE
    TaskBreakfast -> TaskBreakfast : Set Eat breakfast = TRUE
else Hunger FALSE
    FunctionBreakfast -> TaskBreakfast : Return Breakfast ready = FALSE
    TaskBreakfast -> TaskBreakfast : Set Eat breakfast = FALSE
end

Me -> TaskElevator : Start Task
TaskElevator -> TaskElevator : Check Eat breakfast
alt Eat breakfast = TRUE
    TaskElevator -> TaskElevator : Begin Elevator Process
else Eat breakfast = FALSE
    TaskElevator -> TaskElevator : Begin Elevator Process
end
TaskElevator -> Me : Task Complete
@enduml
```