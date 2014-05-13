### Client Stability
* The game client is free of crashes, freezes, or hangs.
* There are currently no open, 100% reproducible crash bugs in your issue tracking system.
* The standard for client stability is: no more than 1% of user sessions should end in a crash.
* The client should handle common device events/states gracefully, such as Sleep Mode, Network disconnects, 3G connections and phone calls.

### In-Game Purchases
* For the App Store (iOS), no IAP (in-app-purchases) should exceed $99.99 USD (or equivalent if in other currencies).
* If the game uses Promo Codes for unlocking content or acquiring in-game items, it must be EXPLICITLY notified to YMC.
* If the game uses any means other than In-App-Purchases for acquiring content, functionality or services, it must be EXPLICITLY notified to YMC.

### Build Notes, Version # and Title
* The version # for your game must be the same for:
    1. CFBundleVersion
    2. CFBundleShortVersionString
    3. iTunesConnect page (this is the # that is displayed in the App Store - iTunesConnect will generally be handled by YMC).
* Try to minimized the binary size of the game as much as possible. 80MB is maximum we recommend.
* The game must also display the version # on the client, in an appropriate place (i.e., in the settings screen or main menu)
* That game is not referred to as a "Beta" "Demo", "Trial" or "Test" version (App Store Guidelines).
    * Build notes must be provided to YMC with each new build, outlining the latest changes that have been made, in order to allow proper review and testing.

### Game Functionality
* The submission candidate is free of any major game or game system breaks including:
    1. Issues blocking game progression
    2. Game exploits
    3. Non-functional content of any kind (missions, items, characters, levels, monsters, weapons, skills etc)
    4. User Interface errors
    5. Major performance issues, including
        * long load times (how long?)
        * frame rate drops (how low?)
        * unresponsiveness (how to measure?)

### User Registrations and Logins
* The implementation must follow YMC User Credential Flow
* If user deletes the app from their device, they can recover their game status by logging into the game again using existing account.
* No registration-related errors are present in the submission candidate.
* Informative error messages must be served to users who have login issues. Errors must denote the following causes at a minimum:
    * Invalid characters in email / password
    * Invalid email format
    * Username is incorrect
    * Password is incorrect

### Localization Requirements
* No unlocalized text is present in the game
* No unlocalized voice audio is present in the game
* Correct, clear and consistent use of game vocabulary

### Analytics
* YMC Analytics are integrated in the game
* All KPIs specified in the analytics instruction document are implemented in the game by the game specific guidelines
* The functionality of all analytics systems is tested and verified to be complete

Note: Use the Analytics tab on Developer.Ymcgames.com to view analytics events on your test version by clicking on SDK Debug View


### Social Networking Service (SNS) Integration
Note: Social Networking Services are a vital component of modern user acquisition, retention, and engagement strategies.
*The involvement of an outside party (i.e. Facebook, Twitter) does not negate the developer's responsibility for full and polished integration with supported Social Networking Services. Each SNS SDK will provide adequate debugging tools.*
* All SNS related functions, calls, and processes are complete and sufficiently polished.
* All SNS related aspects of your game are free of visual, text, or compatibility issues

#### Platform Specific Requirements:
##### Facebook
* If your game uses FB Registration (aka "Connect with FB"), this should be free of errors and function properly with or without the FB App installed.
* All posted images/pictures appear without corruption, formatting errors, or other issues
* All links on wall posts or other entries function appropriately
* No placeholder or hard-coded strings present.
* The app does not over-spam FB friends (apps that spam too much can be blocked by FB)

##### Twitter
* The app does not violate Twitter's TOS: https://twitter.com/tos

##### Youtube
* The application does not violate YouTube's TOS: http://www.youtube.com/static?gl=CA&template=terms
* Reasonable effort has been made to ensure that any user-generated YouTube content adheres to their Community Guidelines: http://www.youtube.com/t/community_guidelines

### Visual Polish and Audio Fidelity and UI compliance
* The Game is free of any obvious text issues include but not limited:
    * truncation (i.e. "...")
    * text overlapping with other visual elements
    * inappropriately large or small fonts
    * overly inconsistent use of fonts and/or font sizes
    * illegible font colors on top of colored background elements
    * improper size / scale of buttons
* The Game is free of any major visual issues such as:
    * missing or placeholder assets
    * corrupted assets
* The Game is free of any offensive issues such as profane, vulgar, or otherwise offensive dialogue
* The Game also possesses
    * a clear delineation between interactive and non-interactive elements
    * appropriate achievement icons
    * a 'restore purchases' button for games offering non-consumable in-app-purchases

### Final Build Delivery (Submission Candidate)
* The game should not contain the words "Test", "Beta", "Demo", "Trial" anywhere in the title
* The game should not contain any debug buttons, text, functions, cheats or other developer tools
* The game has been tested and verified on all supported devices and operating systems
* The game has been tested and verified in all languages and regions in which is it being launched
* The game contains appropriate (Production) provisioning
* The game does not use any copyrighted materials or Intellectual Property (IP), including Art Assets, belonging to another company.

### Error Handling
Note: Section 2.2 of the App Store Review Guidelines states: "Apps that exhibit bugs will be rejected."

This guideline provides each reviewer with a high degree of freedom to reject a game for exhibiting too many bugs in general.

In an effort to adhere to Section 2.2, your submission candidate should meet the following criteria:

* The submission candidate is generally free of errors, obvious bugs or other "glaring" mistakes
* The game handles client-side errors elegantly
* The game handles server-side errors elegantly
* For all errors, the user is directed to the appropriate venue for support (I.E. support@ymcgames.com)
* The end-user impact of any existing errors is negligible
* All errors display relevant, and human-readable text
* When the servers are down for maintenance, appropriate messages are displayed to end users
