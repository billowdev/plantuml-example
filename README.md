# plantuml-example

##### userAuthorization.puml

![userAuthorization](https://github.com/billowdev/plantulm-example/blob/main/out/usecase-diagram/userAuthorization/userAuthorization.png?raw=true)

```
@startuml
'https://plantuml.com/use-case-diagram

left to right direction

actor "System Administrator" as actorAdmin

rectangle "User Authorization" {
    usecase (Validate Users) as usecaseValidateUsers
    usecase (Check Password) as usecaseCheckPassword

    actorAdmin -- usecaseValidateUsers

    usecaseValidateUsers -> usecaseCheckPassword : <<uses>>

}
@enduml
```