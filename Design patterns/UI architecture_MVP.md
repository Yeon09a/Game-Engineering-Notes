# 𝐈𝐦𝐩𝐫𝐨𝐯𝐢𝐧𝐠 𝐔𝐈 𝐀𝐫𝐜𝐡𝐢𝐭𝐞𝐜𝐭𝐮𝐫𝐞 𝐰𝐢𝐭𝐡 𝐌𝐕𝐏 𝐢𝐧 𝐆𝐚𝐦𝐞 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐦𝐞𝐧𝐭
While participating in a game development project, I began to reconsider UI architecture. In my previous work, I had mainly developed relatively small-scale projects, so I didn’t feel the need of UI design pattern. 


In the existing UI, UI presentation and input handling, state decision logic, and data access logic were all contained within a single class. As a result, the code gradually became longer and more difficult to follow. In addition, as new UI elements and related features were added, I frequently had to modify overall UI code, and UI maintenance became increasingly difficult. Ultimately, this led me to realize that my UI architecture had high coupling and low cohesion.


Through experiencing these issues, I identified the root cause as a architecture in which the UI class referenced the data directly. Consequently, I concluded that the UI architecture needed to be redesigned. During this process, I researched various resources on design patterns and decided to adopt MVP as the UI design pattern, as it allows the UI presentation and data to remain independent of each other.
### The reasons for choosing MVP are as follows:
1. To minimize the responsibility of the UI class. (purely presentational role)
    1. In the existing UI architecture, a single UI class handled UI presentation and input handling, state decision logic, and data access, which violated the Single Responsibility Principle.
    2. I separated responsibilities so that View in MVP handled only UI presentation and input handling, while Presenter handled only State decision logic.
2. To reduce the scope of changes required during maintenance.
    1. Although data was separated from the UI class, the UI class directly referenced it, so  I had to modify UI presentation and input handling, state decision logic, and data access whenever maintenance was required.
    2. In MVP, only Presenter needs to be modified so that it minimizes the effect on the UI and data.
3. To simplify the flow of UI logic.
    1. The more features were added, the more difficult it became to track the flow of the code.
    2. In MVP, I thought it possible to simplify the overall flow through a unidirectional structure such as UI → Presenter → Model and UI ← Presenter ← Model.
### The roles of the View, Presenter, and Model were defined as follows:
1. View : UI presentation and input handling
    - Owns UI components
    - Handles UI activation and deactivation
    - Sets UI data
    
    The View has no knowledge of the UI’s state decision logic and only manages presentation according to the Presenter’s instructions.
    
2. Presenter : State decision logic and Mediator between the View and Model
    - Receives UI events
    - Performs state decision logic
    - Calls Model functions and updates the View with the results
    
    All UI inputs are handled by the Presenter, and the results determined by the Presenter are passed back to the View.
    
3. Model : feature specific classes
    - Handles data processing and executes functionality
    
    Since it was independent of the UI, it didn’t require changes when applying MVP.


After adopting the MVP pattern, the UI class code noticeably became shorter, and it became clear where modifications were needed when adding new UI elements and features. In addition, tracking the overall code flow became easier.


I can’t say the architecture I adopted is perfect, but as I add new UI elements and features, I can work without the difficulties I faced in the previous architecture.


Previously, I thought design patterns were simply one of the options for performance optimization. However, through this experience, I have come to see that design patterns are a design tool for managing complex structures and improving development efficiency.


MVP isn’t a perfect design pattern, but I find it to be a suitable choice in terms of maintainability and extensibility for the current project.


Of course there may be better design patterns. If there are design patterns more effective than MVP, I’d like to learn about them. I am also curious which design patterns other developers are using, and why they choose them.
