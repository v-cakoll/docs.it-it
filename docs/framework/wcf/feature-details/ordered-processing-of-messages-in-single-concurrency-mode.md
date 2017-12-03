---
title: "Elaborazione di messaggi ordinata in modalità di concorrenza singola"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c677ed869c0e5dd0df1288de48668ba403df5aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="1719c-102">Elaborazione di messaggi ordinata in modalità di concorrenza singola</span><span class="sxs-lookup"><span data-stu-id="1719c-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="1719c-103">WCF non garantisce l'ordine in cui vengono elaborati i messaggi, a meno che il canale sottostante sia con sessione.</span><span class="sxs-lookup"><span data-stu-id="1719c-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="1719c-104">Ad esempio, un servizio WCF che utilizza MsmqInputChannel, che non è un canale con sessione, non sarà possibile elaborare messaggi in ordine.</span><span class="sxs-lookup"><span data-stu-id="1719c-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="1719c-105">Ci sono casi in cui uno sviluppatore può vuole che l'ordine nel comportamento di elaborazione ma non si desidera utilizzare sessioni.</span><span class="sxs-lookup"><span data-stu-id="1719c-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="1719c-106">In questo argomento viene descritto come configurare questo comportamento quando un servizio è in esecuzione in modalità di concorrenza singola.</span><span class="sxs-lookup"><span data-stu-id="1719c-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="1719c-107">Elaborazione di messaggi in ordine</span><span class="sxs-lookup"><span data-stu-id="1719c-107">In-order Message Processing</span></span>  
 <span data-ttu-id="1719c-108">A <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è stato aggiunto un nuovo attributo denominato <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1719c-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="1719c-109">Quando l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è impostato su true e <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su <xref:System.ServiceModel.ConcurrencyMode.Single>, i messaggi inviati al servizio verranno elaborati in ordine.</span><span class="sxs-lookup"><span data-stu-id="1719c-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="1719c-110">Nel frammento di codice seguente viene illustrato come impostare questi attributi.</span><span class="sxs-lookup"><span data-stu-id="1719c-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="1719c-111">Se l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su qualsiasi altro valore, viene generato un oggetto <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="1719c-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1719c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1719c-112">See Also</span></span>  
 [<span data-ttu-id="1719c-113">Le sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="1719c-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="1719c-114">Concorrenza</span><span class="sxs-lookup"><span data-stu-id="1719c-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
