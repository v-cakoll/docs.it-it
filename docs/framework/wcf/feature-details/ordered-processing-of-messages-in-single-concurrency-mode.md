---
title: Elaborazione di messaggi ordinata in modalità di concorrenza singola
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: baba75fe398d974f989acfda7ef7366986f6813b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598736"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="fd282-102">Elaborazione di messaggi ordinata in modalità di concorrenza singola</span><span class="sxs-lookup"><span data-stu-id="fd282-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="fd282-103">WCF non fornisce alcuna garanzia sull'ordine in cui i messaggi vengono elaborati, a meno che il canale sottostante non sia con sessione.</span><span class="sxs-lookup"><span data-stu-id="fd282-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="fd282-104">Ad esempio, un servizio WCF che usa MsmqInputChannel, che non è un canale con sessione, non riuscirà a elaborare i messaggi nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="fd282-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="fd282-105">In alcuni casi uno sviluppatore potrebbe volere il comportamento di elaborazione in ordine, ma non usare le sessioni.</span><span class="sxs-lookup"><span data-stu-id="fd282-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="fd282-106">In questo argomento viene descritto come configurare questo comportamento quando un servizio è in esecuzione in modalità di concorrenza singola.</span><span class="sxs-lookup"><span data-stu-id="fd282-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="fd282-107">Elaborazione di messaggi in ordine</span><span class="sxs-lookup"><span data-stu-id="fd282-107">In-order Message Processing</span></span>  
 <span data-ttu-id="fd282-108">A <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è stato aggiunto un nuovo attributo denominato <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fd282-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="fd282-109">Quando l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è impostato su true e <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su <xref:System.ServiceModel.ConcurrencyMode.Single>, i messaggi inviati al servizio verranno elaborati in ordine.</span><span class="sxs-lookup"><span data-stu-id="fd282-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="fd282-110">Nel frammento di codice seguente viene illustrato come impostare questi attributi.</span><span class="sxs-lookup"><span data-stu-id="fd282-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="fd282-111">Se l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su qualsiasi altro valore, viene generato un oggetto <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="fd282-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd282-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd282-112">See also</span></span>

- [<span data-ttu-id="fd282-113">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="fd282-113">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="fd282-114">Concorrenza</span><span class="sxs-lookup"><span data-stu-id="fd282-114">Concurrency</span></span>](../samples/concurrency.md)
