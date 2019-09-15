---
title: Elaborazione di messaggi ordinata in modalità di concorrenza singola
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: ecabb9a6e838b0137c538d76c554646356ea87f5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991508"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="94bb7-102">Elaborazione di messaggi ordinata in modalità di concorrenza singola</span><span class="sxs-lookup"><span data-stu-id="94bb7-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="94bb7-103">WCF non fornisce alcuna garanzia sull'ordine in cui i messaggi vengono elaborati, a meno che il canale sottostante non sia con sessione.</span><span class="sxs-lookup"><span data-stu-id="94bb7-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="94bb7-104">Ad esempio, un servizio WCF che usa MsmqInputChannel, che non è un canale con sessione, non riuscirà a elaborare i messaggi nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="94bb7-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="94bb7-105">In alcuni casi uno sviluppatore potrebbe volere il comportamento di elaborazione in ordine, ma non usare le sessioni.</span><span class="sxs-lookup"><span data-stu-id="94bb7-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="94bb7-106">In questo argomento viene descritto come configurare questo comportamento quando un servizio è in esecuzione in modalità di concorrenza singola.</span><span class="sxs-lookup"><span data-stu-id="94bb7-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="94bb7-107">Elaborazione di messaggi in ordine</span><span class="sxs-lookup"><span data-stu-id="94bb7-107">In-order Message Processing</span></span>  
 <span data-ttu-id="94bb7-108">A <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è stato aggiunto un nuovo attributo denominato <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="94bb7-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="94bb7-109">Quando l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è impostato su true e <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su <xref:System.ServiceModel.ConcurrencyMode.Single>, i messaggi inviati al servizio verranno elaborati in ordine.</span><span class="sxs-lookup"><span data-stu-id="94bb7-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="94bb7-110">Nel frammento di codice seguente viene illustrato come impostare questi attributi.</span><span class="sxs-lookup"><span data-stu-id="94bb7-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="94bb7-111">Se l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su qualsiasi altro valore, viene generato un oggetto <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="94bb7-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bb7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94bb7-112">See also</span></span>

- [<span data-ttu-id="94bb7-113">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="94bb7-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="94bb7-114">Concorrenza</span><span class="sxs-lookup"><span data-stu-id="94bb7-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
