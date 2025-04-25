# Clean-Architecture

Clean architecture is becoming increasingly popular in the Android world. There are tons of articles out there that are helping people get hands-on experience with Clean architecture.

During a recent conversation with one of my friends, I found out that he was struggling to figure out how to properly implement all the layers in the architecture.

I’d like to discuss my perspective on Clean Architecture. Before we proceed, I’d like to acknowledge the original source of origin of Clean Architecture, which you can find through the link below.

However, for the purpose of our conversation, I’ll provide a brief overview of the concept before delving into my insights.

### Project Overview

This project aims to demonstrate the usage of Android Architecture Components and how this components can be used in an application with a MVVM architecture in Kotlin.

### Let's explore Architecture Components
According to Android Documentation, Architecture Components are a set of Android libraries for structuring your app in a way that is robust, testable, and maintainable.

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

Inner layer should not depend on out layer

This implies that the repository should have no dependency on the use case, and similarly, the use case should not depend on the presentation layer ( ViewModel).

#### UI/Presentation

This purely deals with UI and views the system of Android and its state handling.

#### Domain Layer

- The Domain must remain independent of all other layers.
- On the other hand, a use case can have another use case as its dependency, allowing the delegation of responsibilities to the dependent use case. but this can lead to circular dependency in large projects which we need to keep watch on.
- Do not hold any state
- It calls a method of the repository to fetch data without caring how and from where it comes.
- No threading details on the Domain layer.
- I prefer to have a single method in use cases like invoke(..). Many are adding multiple methods to use case.



#### Data Layer

- To ensure flexibility in replacing the data layer library, such as Retrofit, with another library without affecting the domain and UI layers, the data layer should solely consist of the API and a data source for memory.
- It should only depend on api , datasource memory if the data layer depends on anything else it's a red flag

However, for the purpose of our conversation, I’ll provide a brief overview of the concept before delving into my insights.

### Refrences:
  - Android Documentation
  - source code for the official Google I/O 2018 for Android app
  - Architecture Components Code Lab

