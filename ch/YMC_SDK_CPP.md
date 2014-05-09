# YMC C++ SDK 

![Mou icon](http://developer.ymcgames.com/images/ymc-logo.png)

## 概况

游戏开发者可以使用 **YMC SDK** 实现用户帐号管理并统计游戏经营数据。

YMC为使用 **C++** 或 **Cocos2D-x** 引擎开发的游戏提供了Android和iOS版本的SDK头文件和库。

## 起步

开发者可以从YMC的开发者网站下载Android或iOS平台的SDK。

## SDK 内容

SDK的头文件和库文件目录结构如下：

	include/
		YMCU.h
		YMCA.h
		...
	lib/	
		ymcsdk.a
		...

请将其正确放置于游戏代码工程中。

![Import](/images/Screen_Shot_sdk.png)

## YMCU 用户帐号管理

请包含下述头文件：

	#include "YMCU.h"
	
### Initialization 初始化

在使用其它API之前，请先调用

	YMCResult YMCUserInit(YMCUserOptions* ymcUserOptions);
	
*YMCUserOptions* 类型定义：

    typedef struct  {
        char game_id[MAX_GAME_ID_LENGTH];
        int use_test_server;  // 0 <- use live server, 1 <- use test server
    }YMCUserOptions;
	
例子：

    YMCUserOptions userOptions;
    strcpy(userOptions.game_id, YOUR_GAMEID);
    userOptions.use_test_server = 1;
    YMCUserInit( &userOptions );
    	
### 注册YMC用户帐号：
  
	YMCResult YMCUserRegister(eMail, password, username,NULL,NULL, NULL,
                          (YMCUOnSuccess)OnSuccess,
                          (YMCUOnError)OnError);
                          
大部分YMCU API是以异步方式工作的，调用时须传递下面两个回调函数指针：

    void OnError(char* error_response, void* pdata);
    void OnSuccess(YMCUserSession *puserSession, void *pdata)

例子：

    void OnError(char* error_response, void* pdata)
    {
    	CCLOG("Error! ");
    	CCLOG("%s", error_response);
        //...
    }

    void OnSuccess(YMCUserSession *puserSession, void *pdata)
    {
    	CCLOG("Success! ");
    	CCLOG("access_token: %s", puserSession->access_token);
    	CCLOG("user_id: %d",puserSession->user_id);
    	CCLOG("expires: %d",puserSession->expires);
    
    	//...
    }

    YMCResult result;
    result = YMCUserRegister(eMail, password, username,NULL,NULL, NULL,
                          (YMCUOnSuccess)OnSuccess,
                          (YMCUOnError)OnError);
                         
### 登录

适用于已注册的用户帐号： 

	YMCResult result;
	result = YMCUserLogin(eMail, password, username, NULL,
                          (YMCUOnSuccess)OnSuccess,
                          (YMCUOnError)OnError);
        CCLOG("Login Result: %d",result);
    

### 登出

	YMCResult result;
    result = YMCUserLogout(&currentSession, NULL, NULL, NULL);
    CCLOG("Logoff Result: %d",result);
    
### 获取当前用户详情
YMC用户帐号定义如下：

    typedef struct {
        char user_name[MAX_USER_NAME_LENGTH];
        char email[MAX_EMAIL_LENGTH];
        char first_name[MAX_NAME_LENGTH];
        char last_name[MAX_NAME_LENGTH];
        char gender[MAX_NAME_LENGTH];
        char gamesJSON[MAX_JSON_STRING];
    } YMCUser;
    
获取当前Session的用户详情：

	YMCResult YMCUserGetInfo(YMCUserSession* userSession,
                            void* pdata,
                            YMCUOnSuccessUserInfo OnSuccess,
                            YMCUOnError OnError);
"OnSuccess"回调函数类型定义如下：

	typedef void (*YMCUOnSuccessUserInfo)(YMCUser* puser, void* pdata);
                           
### 忘记密码

使用此API重置密码：

	YMCResult YMCUserPasswordForgot(const char* email,
                                    void* pdata,
                                    YMCUOnSuccessForgot OnSuccessForgot,
                                    YMCUOnError OnError);
     

## YMC经分系统

要使用YMC经分系统，请在头文件放入：

	#include "YMCA.h"

### 初始化
请使用YMC ID初始化:

	yaInit(YOUR_GAMEID);

### 记录游戏内购
使用 yaCharge 来纪录任何玩家游戏内购。 

    void yaCharge(const char *currency, double value);
    
例子：

     yaCharge("USD",6.99);
     yaCharge("RMB",35);


### yaEvent 经分事件
yaEvent描述了当前游戏中需要被记录下来以便随后系统分析的各种事件。
	
### 记录自定义事件
如果需要记录特定的游戏事件，可以构造和定制yaEvent加以描述：

    yaEvent *yaEventCreate(const char *name);

    //添加数字属性：
    void yaAddNumber(yaEvent *event,const char*key,double value);

    //添加字符串属性：
    void yaAddString(yaEvent *event,const char *key, const char *value); 

然后记录此事件：
    
    void yaTrack(yaEvent *event);		

例子：

	yaEvent *evt = yaEventCreate("Level_Up");
	yaAddString(evt, "Beat", "Playerx");
	yaAddNumber(evt, "Level", 10);
	yaTrack(evt);

