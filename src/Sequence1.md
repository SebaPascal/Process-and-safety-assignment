# First sequence diagram: Comunication between tasks

For the first sequence diagram, I will explain the interactions between my tasks. For instance, after finishing breakfast, I immediately start preparing my things for the university. This diagram will illustrate how these tasks communicate and transition from one to the next.

```plantuml
skinparam backgroundColor transparent
@startuml
actor User as U
participant "Morning routine" as S

U -> S : Wake up
S --> U : Alarm sounds

U -> S : Get up
S -> S : Go to shower
S -> S : Get dress

U -> S : Evaluate hunger
alt Hunger = "Yes"
  S -> S : Prepare Breakfast
  S -> S : Go to kitchen
  S -> S : Prepare toast, eggs and tea
  S -> S : Eat
else Hunger = "No"
  S -> S : go directly to the elevator
end

S -> S : Wait for elevator
S -> S : enter elevator
S --> U : Get on elevator
@enduml
```