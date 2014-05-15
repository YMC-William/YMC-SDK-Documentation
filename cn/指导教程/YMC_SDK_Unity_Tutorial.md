# YMC SDK Unity 3D 指导教程
![Mou icon](http://developer.ymcgames.com/images/ymc-logo.png)

## 概况

这个指导教程会带您如何安装 **YMC SDK 给 Unity**。 完成这个教程，您会有一个游戏的外壳。 我们会专注iOS平台。

## 起步

您需要完成这个教程的文档在这个zip挡里。

下载: [https://developer.ymcgames.com/tutorials/assets/YMCSDKTutorial2.0.6.zip]()

提示：您需要一个在 YMC Games 可用的 Game ID 才可以使用YMC经分系统！

**您必须要从苹果开发者中心获得正确的provisioning如果您想要在您的手机或平板上测试。**

## 步骤

1. 登陆 developer.ymcgames.com 然后选择 ”资源“ -> “SDK 下载”。

![image](/images/part1.jpg)

2. 在SDK底下您可以找到我们YMC的SDK.
3. 下载您要开发用的Unity YMC SDK
4. 在这个指导教程里先下载最新SDK。

![image](/images/part2.jpg)

5. 解压缩您下载的 Zip 档。
6. 开启 Unity.
7. 建造一个新项目叫 "YMCTutorial"
8. 在 "Project" 标签里，右键点击 "Assets" 文件夹，然后 “Import Package > Custom Package“，再选您解压缩的 YMC Unity SDK 文档。
9. 在这个指导教程里，选 iOS 的版本。

![image](/images/part3.jpg)
![image](/images/part4.png)

10. 解压缩 "TutorialScripts.zip"。然后把文档拉进到 "Assets" 质料夹里。

![image](/images/part5.jpg)

11. 点进 "TutorialScripts.cs"。 这会开启 MonoDevelop 来编辑文档。
12. 现在您需要您的 Game ID。
13. 请到 developer.ymcgames.com 登陆。
14. 游览到您的游戏页面。

![image](/images/part6.jpg)

15. 您可以找到YMC游戏ID在游戏信息里。
16. YMC ID 就是您游戏的ID。
18. 选取然后拷贝您的 YMC ID。

18. 回到 TutorialScripts1.cs 在 MonoDevelop 里，寻找这条字串：

	private static string GAMEID = "replace_this_with_your_game_id";
	
19. 请把 replace_this_with_your_game_id 换成您拷贝的 YMC ID。然后储存。

20. 开启 “TutorialScript.cs”：

![image](/images/part7.jpg)

21. 寻找这条字串:

	private static string GAMEID = "replace_this_with_your_game_id";
	
22. 请把 replace_this_with_your_game_id 换成您拷贝的 YMC ID。然后储存。
23. 回到 Unity，请选择 "File -> Save Scene"，储存名称为 “TutorialScene1“。
24. 在 "Hierarchy" 标签里，点 "Main Camera"。
24a. 在 “Inspector” 底下，点击 “Add Component“。
24b. 选 “Scripts”
24c. 选 “Tutorial Script 1“
24d. 储存。
25. 现在您第一个游戏界面就完成了！

26. 现在我们在建立第二个界面。请选择 “File -> New Scene“。
27. 在 “Hierarchy“ 标签里点选 “Main Camera“。
27a. 在 “Inspector” 底下，点击 “Add Component“。
27b. 选 “Scripts”
27c. 选 “Tutorial Script 2“
27d. 储存。
28. 现在在"Assets"标签里，点击 "TutorialScene1" 两次。
29. 现在点中间上方的 Play 按钮来测试。
30. 在点击同一个Play 按钮，测试就会结束。

提示: 所有的功能不能运作如果不是在iOS 的机子或模拟器上！在 Unity 上试跑只是确认没有巨大的错误。

31. 现在选 “File -> Build Settings“
32. 在 “Platform“ 区底下，选择 “iOS“ 再按 “Switch Platform“。

![image](/images/BuildSettings.jpg)

33. 然后把 TutorialScene1 和 TutorialScene2 从 Assets 拉进 "Scenes In Build" 区。请确认 TutorialScene1 在上面。

![image](/images/BuildSettings2.jpg)

34. “Build Settings” 里，点选 “Player Settings...“。
35. 在 “Optimization”里， SDK Version 要选成 “Simulator SDK”。

![image](/images/PlayerSettings.jpg)

36. 回到 “Build Settings”，点击 "Build and Run"。
37. 把您的建造取名为 "TutorialBuild" 然后储存。

38. 现在 Unity 会把您的代码转给Xcode来编然后在iOS Simulator 里运作。这可能要等几分钟。

提示: 如果 Xcode 无法启动您的游戏，您可以从试利用不同的“Target iOS Version” 在 “Player Setting” 里。请试 “6.0“， 然后在试一边。您可能必须要写过您第一个build。

![image](/images/PlayerSettings2.jpg)

39. Xcode 很有可能会冒出两个错误；这是可以解决的。
40. 首先点选 “Unity-iPhone“ （会有一个Unity的图标在旁边）。

![image](/images/XCodeError.jpg)

41. 按 “Build Phases”。
42. 点击 “Link Binary With Libraries“ 来显示这个项目。

43. 点击 下方的”＋“符号，在选择 ”AdSupport.framework“ 然后点击， ”Add“。

![image](/images/BuildSettingList.jpg)
![image](/images/AdFramework.jpg)

44. 现在在Xcode里点”Play“图表按钮。
45. 如果没有出错，哪就没问题了！可是如果要真正测试SDK，您必须要在一个世纪上的手机或平板电脑上测试。
46. 点击 ”Stop“ 图表就会停下模拟。

47. 如果要在手机或平板电脑上测试，您必需要有从 Apple Developer 正确的 provisioning 和 凭证。
48. 得到您需要的provisioning以后，您就可以在Unity里把“SDK Version” 换成 “Device SDK” 在 “Player Setting...“ 里。
49. 点击 “Build and Run” 后就可以透过Xcode把您的游戏放在您的设备上！

提示: 您可能会遇到Xcode错误。请看步骤31到36来解决。

50. App 在您的设备上运作后，您就可以在YMC 开发者中心登陆。
51. 登陆后您就可以到您的游戏页面点击“显示数据分析系统”。

![image](/images/AnalyticsButton.jpg)

52. 在 “工具“ 底下， 您点击 ”SDK调试视图“
53. 在这里您就可以看到YMC SDK 记录下来的的事件。列如：App 启动，登陆，内购，升级，等等。
54. 如果没有东西显示，请压“刷新”按钮。
55. 如果您的动作有出现，哪应该就完成了！

## 成果

![image](/images/Scene1.png)
![image](/images/Scene2.png)
