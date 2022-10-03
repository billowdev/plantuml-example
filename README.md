# plantuml-example

##### userAuthorization.puml

<!-- ![userAuthorization](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/userAuthorization/userAuthorization.png) -->

<img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/userAuthorization/userAuthorization.png" width="600" title="userAuthorization">


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
<!-- ![userAuthorization](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/creditCardValidationSystem/creditCardValidationSystem.png) -->

<img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/creditCardValidationSystem/creditCardValidationSystem.png" width="600" title="creditCardValidationSystem">

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
<!-- ![userAuthorization](https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/recievedCall/recievedCall.png) -->

<img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/recievedCall/recievedCall.png" width="600" title="recievedCall">

```java
@startuml
'https://plantuml.com/use-case-diagram

actor "ผู้รับโทรศัพท์" as actorCallReciever

rectangle "การรับโทรศัพท์" as revievedCall {
    usecase (รับโทรศัพท์) as usecaseRecieve
    usecase (รับสายเรียกซ้อน) as usecaseCallWaiting

    actorCallReciever -- usecaseRecieve
    usecaseRecieve <. usecaseCallWaiting : <<extends>>
}
@enduml
```


##### studentRegister.puml
<img src="https://raw.githubusercontent.com/billowdev/plantuml-example/main/out/usecase-diagram/studentRegister/studentRegister.png" width="600" title="studentRegister">

```java
@startuml
left to right direction
actor "เจ้าหน้าที่" as actorRegisterationOfficer
actor "นักศึกษา" as actorStudent

rectangle "การลงทะเบียนเรียนของนักศึกษา" as rectangleRegisterationOfStudent {
    usecase (ลงทะเบียนนักศึกษาใหม่) as usecaseRegisterOfNewStudent
    usecase (ลงทะเบียนนักศึกษาปัจจุบัน) as usecaseRegisterOfPresentStudent
    usecase (เก็บหลักฐาน) as usecaseKeepEvidence
    usecase (ชำระเงินค่าเล่าเรียน) as usecasePayRegisterationFee
    usecase (มีเงินไม่พอชำระค่าเล่าเรียน) as usecaseNotHaveEnoughMoneyForPayEducationFee
    usecase (หลักฐานไม่พร้อม) as usecaseEvidenceNotReady
    usecase (ได้รับการยกเว้นค่าเล่าเรียน) as usecaseExceptEducationFee

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