# First state diagram: Breakfast

My first task focuses on my morning routine when I get up take a shower and have breakfast. Typically, I eat bread with something and drink tea, so I will create a state diagram based on this. The process includes waking up, getting out of bed, taking a shower, and then having breakfast.

```plantuml
@startuml
skinparam backgroundColor transparent
'skinparam linetype ortho'
[*] --> WakeUp : Alarm sounds
WakeUp -l-> GetUp
GetUp --> Shower : Go to shower
Shower -r-> Dress : Finish showering
Dress --> EvaluateHungry : "Am i hungry?"

EvaluateHungry --> PrepareBreakfast : Yes
PrepareBreakfast -l-> Kitchen : Go to kitchen
Kitchen -l-> EatBreakfast : Toast, Eggs and Tea
EatBreakfast -l-> GoElevator : Finish Breakfast

EvaluateHungry --> GoElevator : No

GoElevator --> WaitElevator : Press elevator button
WaitElevator -r-> EnterElevator : Elevator arrives
EnterElevator --> [*]
@enduml
```