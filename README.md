# plantuml-example

##### userAuthorization.puml

![userAuthorization](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/userAuthorization/userAuthorization.png)

<!-- <img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/userAuthorization/userAuthorization.png" width="600" title="userAuthorization"> -->


```java
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



##### creditCardValidationSystem.puml
![creditCardValidationSystem](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/creditCardValidationSystem/creditCardValidationSystem.png)

<!-- <img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/creditCardValidationSystem/creditCardValidationSystem.png" width="600" title="creditCardValidationSystem"> -->

```java
@startuml
'https://plantuml.com/use-case-diagram

skinparam sequence {
'ArrowColor DeepSkyBlue
'ActorBorderColor DeepSkyBlue
'LifeLineBorderColor blue
'LifeLineBackgroundColor #A9DCDF

'ParticipantBorderColor DeepSkyBlue
'ParticipantBackgroundColor DodgerBlue
ParticipantFontName Thai
ParticipantFontSize 17
'ParticipantFontColor #A9DCDF

'ActorBackgroundColor blue
ActorFontColor black
ActorFontSize 17
ActorFontName Thai
}


' -------------------------
left to right direction

actor "Customer" as actorCustomer
actor "Retail Insitution" as actorRetailInstitution
actor "Sponsoring Financial Institution" as actorSponsoringFinancialInstitution

rectangle  "Credit Card Validation System" {
   usecase (Perform Card Transaction) as usecasePerformCardTransaction
   usecase  (Process Customer Bill) as usecaseProcessCustomerBill
   usecase (Recocile Transactions) as usecaseRecocileTransactions
   usecase (Manage Customer Account) as usecaseManageCustomerAccount

    actorCustomer -- usecasePerformCardTransaction
    actorCustomer -- usecaseProcessCustomerBill
    actorCustomer -- usecaseManageCustomerAccount

    usecaseProcessCustomerBill -- actorRetailInstitution
    usecasePerformCardTransaction -- actorRetailInstitution
    usecaseRecocileTransactions -- actorRetailInstitution

    usecaseProcessCustomerBill -- actorSponsoringFinancialInstitution
    usecaseManageCustomerAccount -- actorSponsoringFinancialInstitution
}
' ----------------------------
@enduml
```


##### recievedCall.puml
![recievedCall](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/recievedCall/recievedCall.png)

<!-- <img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/recievedCall/recievedCall.png" width="600" title="recievedCall"> -->

```java
@startuml
'https://plantuml.com/use-case-diagram

actor "??????????????????????????????????????????" as actorCallReciever

rectangle "??????????????????????????????????????????" as revievedCall {
    usecase (?????????????????????????????????) as usecaseRecieve
    usecase (?????????????????????????????????????????????) as usecaseCallWaiting

    actorCallReciever -- usecaseRecieve
    usecaseRecieve <. usecaseCallWaiting : <<extends>>
}
@enduml
```


##### studentRegister.puml
<!-- <img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/studentRegister/studentRegister.png" width="600" title="studentRegister"> -->

![studentRegister](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/studentRegister/studentRegister.png)

```java
@startuml
left to right direction
actor "?????????????????????????????????" as actorRegisterationOfficer
actor "????????????????????????" as actorStudent

rectangle "????????????????????????????????????????????????????????????????????????????????????" as rectangleRegisterationOfStudent {
    usecase (???????????????????????????????????????????????????????????????) as usecaseRegisterOfNewStudent
    usecase (???????????????????????????????????????????????????????????????????????????) as usecaseRegisterOfPresentStudent
    usecase (?????????????????????????????????) as usecaseKeepEvidence
    usecase (????????????????????????????????????????????????????????????) as usecasePayRegisterationFee
    usecase (?????????????????????????????????????????????????????????????????????????????????) as usecaseNotHaveEnoughMoneyForPayEducationFee
    usecase (?????????????????????????????????????????????) as usecaseEvidenceNotReady
    usecase (?????????????????????????????????????????????????????????????????????????????????) as usecaseExceptEducationFee

    actorRegisterationOfficer -- usecaseRegisterOfNewStudent
    actorRegisterationOfficer - usecaseRegisterOfPresentStudent
    usecasePayRegisterationFee -- actorStudent

    usecaseRegisterOfNewStudent -> usecasePayRegisterationFee : <<uses>>
    usecaseRegisterOfNewStudent -> usecaseKeepEvidence : <<uses>>

    usecaseRegisterOfPresentStudent --> usecasePayRegisterationFee : <<uses>>
    usecaseRegisterOfPresentStudent --> usecaseKeepEvidence : <<uses>>

    usecaseEvidenceNotReady ..> usecaseKeepEvidence : <<extends>>

    usecaseExceptEducationFee <.. usecasePayRegisterationFee  :<<extends>>
    usecaseNotHaveEnoughMoneyForPayEducationFee  <.. usecasePayRegisterationFee :<<extends>>

}
@enduml
```