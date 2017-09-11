---
title: 'Attenuazione: chiamate al metodo EventSource.WriteEvent'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 270f89183bced5d07598b1731f18acf90ec9715a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a><span data-ttu-id="6e471-102">Attenuazione: chiamate al metodo EventSource.WriteEvent</span><span class="sxs-lookup"><span data-stu-id="6e471-102">Mitigation: EventSource.WriteEvent Method Calls</span></span>
<span data-ttu-id="6e471-103">[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] applica un contratto tra un metodo di evento ETW in una classe derivata da <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> e il metodo <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> della relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="6e471-103">The [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] enforces a contract between an ETW event method in a class that is derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> and  the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method of its base class.</span></span> <span data-ttu-id="6e471-104">Il metodo di evento ETW deve passare al metodo <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> l'ID evento seguito dagli stessi argomenti passati al metodo di evento.</span><span class="sxs-lookup"><span data-stu-id="6e471-104">The ETW event method must pass the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method the event ID followed by the same arguments that were passed to the event method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="6e471-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="6e471-105">Impact</span></span>  
 <span data-ttu-id="6e471-106">Un metodo di evento ETW definito nel modo seguente rompe il contratto:</span><span class="sxs-lookup"><span data-stu-id="6e471-106">An ETW event method defined in the following way breaks the contract:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
```  
  
 <span data-ttu-id="6e471-107">Quando questo contratto viene violato, viene generata un’eccezione <xref:System.IndexOutOfRangeException> se un oggetto <xref:System.Diagnostics.Tracing.EventListener> legge i dati nel processo <xref:System.Diagnostics.Tracing.EventSource> .</span><span class="sxs-lookup"><span data-stu-id="6e471-107">When this contract is violated, an <xref:System.IndexOutOfRangeException> exception is thrown at run time if an <xref:System.Diagnostics.Tracing.EventListener> object reads <xref:System.Diagnostics.Tracing.EventSource> data in process.</span></span>  
  
 <span data-ttu-id="6e471-108">La definizione del metodo di evento ETW deve seguire un questo modello:</span><span class="sxs-lookup"><span data-stu-id="6e471-108">The definition for this ETW event method should follow this pattern:</span></span>  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
```  
  
## <a name="mitigation"></a><span data-ttu-id="6e471-109">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="6e471-109">Mitigation</span></span>  
 <span data-ttu-id="6e471-110">È necessario modificare il codice esistente per rispettare lo schema richiesto.</span><span class="sxs-lookup"><span data-stu-id="6e471-110">You must modify existing code to conform to the required pattern.</span></span>  
  
 <span data-ttu-id="6e471-111">È possibile ridurre la quantità di codice che è necessario modificare definendo due metodi per chiamare il metodo <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6e471-111">You can minimize the amount of code that you have to change by defining two methods for calling the <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> method, as follows:</span></span>  
  
```  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e471-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e471-112">See Also</span></span>  
 [<span data-ttu-id="6e471-113">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="6e471-113">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

