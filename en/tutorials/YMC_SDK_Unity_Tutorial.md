# YMC SDK Tutorial for Unity3D
![Mou icon](http://developer.ymcgames.com/images/ymc-logo.png)

## Overview

This tutorial is to guide you on implementing the **YMC SDK for Unity**. At the end of this tutorial, you should have a working multi-scene frame for a game. This tutorial will focus on the iOS platform.

## Getting Started

Download this zip which contains all the files you will need for the tutorial.

Download here: [https://developer.ymcgames.com/tutorials/assets/YMCSDKTutorial2.0.6.zip]()

Note: You will need a game ID that has been approved by YMC before you can get the login section to work!

**You will also need proper provisioning from Apple Developer if you plan on putting your game on to a device.**

## Steps

1. Sign in to developer.ymcgames.com and click on Resources then SDK Downloads.

![](/images/part1.jpg)

2. Under the SDK section on the right you can find our SDKs
3. Download the YMC SDK plugin pack for Unity for the platform you are developing for.
4. For this tutorial download the latest Unity SDK

![](/images/part2.jpg)

5. Unzip the file you downloaded.
6. Launch Unity.
7. Create a new project called "YMCTutorial"
8. In the "Project" tab, right click on the "Assets" folder and "Import Package > Custom Package” and navigate to where you unzipped the YMC Unity SDK.
9. Select the package you want to import (for the purpose of this tutorial import the iOS version)

![Import](/images/part3.jpg)
![Import](/images/part4.png)

10. Now unzip TutorialScripts.zip. Then drag and drop the scripts into the “Assets” folder of the “Project” tab.

![Import](/images/part5.jpg)

11. Double click on “TutorialScript1.cs” and MonoDevelop should load and open the script.
12. Now we need your YMC Game ID which is specific to your game.
13. Navigate to developer.ymcgames.com and login.
14. Navigate to your Games page.

![Import](/images/part6.jpg)

15. You can find your YMC Game ID under the “Game” under the Tasks bar.
16. The Game ID is the YMC ID.
17. Highlight and copy your YMC ID.

18. Back to the TutorialScript1.cs script in MonoDevelop, find the line that says:

	private static string GAMEID = "replace_this_with_your_game_id";
	
19. Replace the string with your GameID and save.

20. Open “TutorialScript2.cs” which can be found on the sidebar in MonoDevelop:

![Import](/images/part7.jpg)

21. Find the line that says:

	private static string GAMEID = "replace_this_with_your_game_id";
	
22. Replace the string with your GameID and save.

23. Back to Unity, go to “File” and “Save Scene”, name it “TutorialScene1”
24. Now find the “Hierarchy” tab, click on the “Main Camera” object.
24a. Under the “Inspector”, click “Add Component”.
24b. Then “Scripts”
24c. Select “Tutorial Script 1”
24d. Save the scene.

25. Now your first scene is setup!

26. Now create a second scene by going to “File” and “New Scene”.
27. Select the “Main Camera” object in the “Hierarchy” tab.
27a. Under the “Inspector”, click “Add Component”
27b. Then “Scripts”
27c. Select “Tutorial Script 2”
27d. Save the scene.
28. Now under the “Assets” tab, double click the Scene, “TutorialScene1”
29. Now press the play icon at the center top, to test if it runs!
30. Now, click the same play icon to stop.

NOTE: The functions won’t work unless if it’s on a device or simulator! Running it in Unity is just a check to ensure the application doesn’t have any major errors.

31. Now go to “File” > “Build Settings”
32. Under the “Platform” section, select the “iOS” option and click “Switch Platform”.

![Import](/images/BuildSettings.jpg)

33. Now with the “Build Settings” open, drag and drop “TutorialScene1” and “TutorialScene2” scene files into the “Scenes In Build” section. Make sure “TutorialScene1” is at the top.

![Import](/images/BuildSettings2.jpg)

34. Under “Build Settings”, click on “Player Settings...”.
35. Scroll down if necessary and under “Optimization”, the SDK Version should be “Simulator SDK”. If not, click on the drop down menu and change it to “Simulator SDK”.

![Import](/images/PlayerSettings.jpg)

36. Back to the “Build Settings”, click “Build and Run”
37. Name your iOS build as “TutorialBuild” and save.

38. Now Unity will convert your code and give it to XCode to compile to run it in an official iOS Simulator. This may take a few minutes for XCode to start and run.

NOTE: If XCode fails to launch, you can retry with a different “Target iOS Version” under the “Player Settings”. This depends on the version of XCode you have. Try “6.0”. You will have to save over/replace your first build.

![Import](/images/PlayerSettings2.jpg)

39. It is likely XCode will throw two errors, which can be fixed.
40. First click on the “Unity-iPhone” with the Unity icon beside it.

![Import](/images/XCodeError.jpg)

41. Press the “Build Phases” tab.
42. Click on “Link Binary With Libraries” to display its items.

43. Click on the “+” sign at the bottom and select “AdSupport.framework” and click “Add”

![Import](/images/BuildSettingList.jpg)
![Import](/images/AdFramework.jpg)

44. Now hit the “Play” icon in XCode to recompile again.
45. If the program loads then everything should be implemented correctly. However for the SDK to function fully, it has to run from a device.
46. Press the “Stop” icon in XCode to stop the simulation.

47. To run it on a device, you will need the proper provisioning and signing certificates from Apple’s Developer website.
48. Once you have a proper provisioning profile for your device, go back to Unity and change the “SDK Version” to “Device SDK” under “Player Settings…”
49. Then hit “Build and Run” to get XCode to build and run it your device!

NOTE: You may run into the same linking error. Refer to step 31 to step 36 to fix.

50. Once the device is running your tutorial app, you can log into YMC Developer portal.
51. Go to the game page that has the same “Game ID” as the tutorial and click the “Show Analytics” button.

![Import](/images/AnalyticsButton.jpg)

52. Under the “Tools” section, click on the “SDK Debug View”
53. This should show all the actions that the YMC SDK tracks such as Launch App, Login, In-App Purchase, Level Up, etc.
54. If nothing is showing up try clicking “Reload”
55. If your actions show up, such as the “Purchase” button, “Login” or “Logoff”, then everything should be working!

## End Result

![](/images/Scene1.png)
![](/images/Scene2.png)
