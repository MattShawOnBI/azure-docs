---
ms.service: logic-apps
ms.topic: include
author: ecfan
ms.author: estfan
ms.date: 10/15/2022
---

To estimate more accurate consumption costs, consider the possible number of messages or events that might arrive on any given day, rather than base your calculations on only the polling interval. When an event or message meets the trigger criteria, many triggers immediately try to read any and all other waiting events or messages that meet the criteria. This behavior means that even when you select a longer polling interval, the trigger fires based on the number of waiting events or messages that qualify for starting workflows. Triggers that follow this behavior include Azure Service Bus and Azure Event Hubs.

So, for example, suppose you set up trigger that checks an endpoint every day. When the trigger checks the endpoint and finds 15 events that meet the criteria, the trigger fires and runs the corresponding workflow 15 times. Azure Logic Apps meters all the actions that those 15 workflows perform, including the trigger requests. To calculate your potential costs, try the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/).