---
layout: page
category : musings
---

The internet is cluttered with numerous chat applications. Sure, there are only a few that stand out. Whatsapp, Hangouts and Messenger to name a few. Telegram is also gaining a lot of popularity. A typical person has so many apps to distract him. Perhaps, *time consuming* will be more apt here. Push notifications were meant to address this issue, and they did, but partly. To put in more clearly, push notifications for an app serve only one app. Multiply this with number of apps using push. You get it?. The fact is, there are already some apps that are trying to solve this issue. Mainly 2 strategies are being used.<br/>

* Gain access to the notification daemon. So, instead of the different apps notifying you about some new message, one single app notifies you and gives you the option to choose the app for replying.
* Provide *THE* interface to send all messages no matter what the app, like **loqui.im**. 

Initially, most would go in favour of the second strategy. *One App To use them all*. But is this soltion as efficient as the apps separately? I recently came across a [engineering blog post](https://code.facebook.com/posts/820258981365363/building-mobile-first-infrastructure-for-messenger/er/)  by Facebook. The post highlights the intricacies of real-time messaging and how Facebook was using Iris for the mobile platform of Messenger. In fact, different mobile apps use widely differing technologies. So, if we use this strategy, it is highly likely that we are suppressing the efficiency of some really cool tech, because Hangouts does not sync the same way as Messenger and so does Telegram.

In view of this, it seems that the first option is more suitable to harness the features of different apps as well as staying updated.

With this idea in mind, I have created an open source project [Chatty](https://github.com/light94/Chatty).  This project is based on the awesome *node-webkit* project. The idea is basically to encapsulate all the messaging services within a single window. So, we are not constraining any service and yet taking a step towards being more organised. This would be like keeping a dedicated browser window such that you don't need to traverse through the tabs to find your chat. One, just one native app on your desktop that will have all your chats!!

Let me know if you find this intersting and any suggestions. 
