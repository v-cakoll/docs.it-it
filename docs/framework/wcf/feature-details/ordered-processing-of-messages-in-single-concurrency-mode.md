---
title: Elaborazione di messaggi ordinata in modalità di concorrenza singola
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: bbbc1f62931abda438c3d06b514518b1199b649e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Elaborazione di messaggi ordinata in modalità di concorrenza singola
WCF non garantisce l'ordine in cui vengono elaborati i messaggi, a meno che il canale sottostante sia con sessione.  Ad esempio, un servizio WCF che utilizza MsmqInputChannel, che non è un canale con sessione, non sarà possibile elaborare messaggi in ordine. Ci sono casi in cui uno sviluppatore può vuole che l'ordine nel comportamento di elaborazione ma non si desidera utilizzare sessioni. In questo argomento viene descritto come configurare questo comportamento quando un servizio è in esecuzione in modalità di concorrenza singola.  
  
## <a name="in-order-message-processing"></a>Elaborazione di messaggi in ordine  
 A <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è stato aggiunto un nuovo attributo denominato <xref:System.ServiceModel.ServiceBehaviorAttribute>. Quando l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è impostato su true e <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su <xref:System.ServiceModel.ConcurrencyMode.Single>, i messaggi inviati al servizio verranno elaborati in ordine. Nel frammento di codice seguente viene illustrato come impostare questi attributi.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Se l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su qualsiasi altro valore, viene generato un oggetto <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>Vedere anche  
 [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Concorrenza](../../../../docs/framework/wcf/samples/concurrency.md)
