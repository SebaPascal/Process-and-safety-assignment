# First state diagram: Breakfast

My first task focuses on my morning routine when I get up take a shower and have breakfast. Typically, I eat bread with something and drink tea, so I will create a state diagram based on this. The process includes waking up, getting out of bed, taking a shower, and then having breakfast.

```plantuml
@startuml
[*] --> WakeUp : Start Routine

state WakeUp {
    [*] --> CheckAlertness
    CheckAlertness : Evaluate physical readiness
    CheckAlertness --> StandUp : Alertness OK
    CheckAlertness --> [*] : Alertness NOT OK (loop)
}

state StandUp {
    [*] --> GoToShower : Stand upright, check balance
    GoToShower : Transition to shower area
}

state Shower {
    [*] --> StartShower : Set water temperature to ideal range
    StartShower --> Rinse : Perform rinse cycle (Duration: 2 min)
    Rinse --> SoapApplication : Apply soap evenly
    SoapApplication --> Rinse : Rinse thoroughly (Duration: 2 min)
    Rinse --> ShowerComplete : Turn off water
}

StandUp --> Shower
Shower --> DressUp : Exit shower, proceed to dress

state DressUp {
    [*] --> EvaluateHunger : Put on clothing
    EvaluateHunger : Check internal hunger sensor
    EvaluateHunger --> [*] : Hunger FALSE (skip breakfast)
    EvaluateHunger --> GoToKitchen : Hunger TRUE (prepare breakfast)
}

state GoToKitchen {
    [*] --> PrepareBreakfast : Collect ingredients (bread, eggs, tea)
    PrepareBreakfast --> ToastBread : Toast bread (Duration: 1 min)
    ToastBread --> CookEggs : Cook eggs (Duration: 3 min)
    CookEggs --> BrewTea : Boil water, brew tea (Duration: 2 min)
    BrewTea --> BreakfastComplete : Assemble meal
}

DressUp --> GoToKitchen : Hunger TRUE
GoToKitchen --> BreakfastComplete : Breakfast ready

BreakfastComplete --> Elevator
[*] --> Elevator

@enduml
```