# Clean-Architecture

Clean architecture is becoming increasingly popular in the Android world. There are tons of articles out there that are helping people get hands-on experience with Clean architecture.

During a recent conversation with one of my friends, I found out that he was struggling to figure out how to properly implement all the layers in the architecture.

I’d like to discuss my perspective on Clean Architecture. Before we proceed, I’d like to acknowledge the original source of origin of Clean Architecture, which you can find through the link below.

However, for the purpose of our conversation, I’ll provide a brief overview of the concept before delving into my insights.

#### Presentation/UI

- This layer deal with handling the UI part
- It contains Activity, Fragment, ViewModel, and imports with the Android package
- This is a pure Android library or application module in the multi-module application

#### Domain

- This layer deal with the Business logic part
- It contains Usecase, a Repository interface
- This is a pure Java/Kotlin module in the multi-module application

#### Data

- This layer deal with all Data related part like fetch, store etch
- It Contains Repository Implementation from the case
- This can be a pure Java/ Kotlin module based on the library you used in the multi-module application

#### My points on the clean architecture 
