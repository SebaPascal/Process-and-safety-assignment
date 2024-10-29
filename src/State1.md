# First state diagram: Breakfast

My first task focuses on my morning routine when I get up take a shower and have breakfast. Typically, I eat bread with something and drink tea, so I will create a state diagram based on this. The process includes waking up, getting out of bed, taking a shower, and then having breakfast.

```plantuml
@startuml
[*] -l-> WakeUp : Start Routine

state WakeUp {
    [*] --> CheckAlarm
    CheckAlarm : Alarm is sounding
    CheckAlarm --> StandUp : turn off
    CheckAlarm --> [*] : Alarm NOT sound
}

state StandUp {
    [*] --> GoToShower : Stand upright
    GoToShower : Transition to shower area
}

state Shower {
    [*] --> StartShower : Set water temperature to ideal range
    StartShower --> Rinse : Start rinse cycle 
    Rinse --> SoapApplication : Apply soap evenly
    SoapApplication --> Rinse : Rinse thoroughly
    Rinse --> ShowerComplete : Turn off water
}

StandUp --> Shower
Shower -r-> DressUp : Exit shower, proceed to dress

state DressUp {
    [*] --> EvaluateHunger : Put on clothing
    EvaluateHunger : Check hunger
    EvaluateHunger --> [*] : Hunger FALSE (skip breakfast)
    EvaluateHunger --> GoToKitchen : Hunger TRUE (prepare breakfast)
}

state GoToKitchen {
    [*] --> PrepareBreakfast : Collect ingredients (bread, eggs, tea)
    PrepareBreakfast --> ToastBread : Proceed to toast bread
    ToastBread --> CookEggs : Proceed to cook eggs
    CookEggs --> BrewTea : Boil water, brew tea 
    BrewTea --> BreakfastComplete : Assemble meal
}

BreakfastComplete --> Elevator

@enduml
```