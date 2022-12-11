Given the conditions of this environment, it's possible for your app components to be launched individually and out-of-order, and the operating system or user can destroy them at any time. Because these events aren't under your control, you shouldn't store or keep in memory any application data or state in your app components, and your app components shouldn't depend on each other.

## Separation of concerns
 - It's a common mistake to write all your code in an [`Activity`](https://developer.android.com/reference/android/app/Activity) or a [`Fragment`](https://developer.android.com/reference/android/app/Fragment)
 - To provide a satisfactory user experience and a more manageable app maintenance experience, it's best to minimize your dependency on them.
## Drive UI from data models
 -   Your users don't lose data if the Android OS destroys your app to free up resources.
-   Your app continues to work in cases when a network connection is flaky or not available.
## Single source of truth
-   It centralizes all the changes to a particular type of data in one place.
-   It protects the data so that other types cannot tamper with it.
-   It makes changes to the data more traceable. Thus, bugs are easier to spot.

## Unidirectional Data Flow
In UDF, **state** flows in only one direction. The **events** that modify the data flow in the opposite direction.
![[typical app architecture.png]]
## UI layer
-   UI elements that render the data on the screen. You build these elements using Views or [Jetpack Compose](https://developer.android.com/jetpack/compose) functions.
-   State holders (such as [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) classes) that hold data, expose it to the UI, and handle logic.
## Data layer
-   Exposing data to the rest of the app.
-   Centralizing changes to the data.
-   Resolving conflicts between multiple data sources.
-   Abstracting sources of data from the rest of the app.
-   Containing business logic.
## Domain layer
TimeZone 과 같은 UseCase

## Manage dependencies between components
- Hilt is best

## General best practices
- **Don't store data in app components.**
- **Reduce dependencies on Android classes.**
- **Create well-defined boundaries of responsibility between various modules in your app.**
- **Expose as little as possible from each module.**
- **Focus on the unique core of your app so it stands out from other apps.**
- **Consider how to make each part of your app testable in isolation.**
- **Types are responsible for their concurrency policy.**
- **Persist as much relevant and fresh data as possible.**
## Benefits of Architecture
-   It improves the maintainability, quality and robustness of the overall app.
-   It allows the app to scale. More people and more teams can contribute to the same codebase with minimal code conflicts.
-   It helps with onboarding. As Architecture brings consistency to your project, new members of the team can quickly get up to speed and be more efficient in less amount of time.
-   It is easier to test. A good Architecture encourages simpler types which are generally easier to test.
-   Bugs can be investigated methodically with well defined processes.