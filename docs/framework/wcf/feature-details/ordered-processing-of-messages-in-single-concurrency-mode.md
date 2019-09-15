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
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Elaborazione di messaggi ordinata in modalità di concorrenza singola
WCF non fornisce alcuna garanzia sull'ordine in cui i messaggi vengono elaborati, a meno che il canale sottostante non sia con sessione.  Ad esempio, un servizio WCF che usa MsmqInputChannel, che non è un canale con sessione, non riuscirà a elaborare i messaggi nell'ordine. In alcuni casi uno sviluppatore potrebbe volere il comportamento di elaborazione in ordine, ma non usare le sessioni. In questo argomento viene descritto come configurare questo comportamento quando un servizio è in esecuzione in modalità di concorrenza singola.  
  
## <a name="in-order-message-processing"></a>Elaborazione di messaggi in ordine  
 A <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è stato aggiunto un nuovo attributo denominato <xref:System.ServiceModel.ServiceBehaviorAttribute>. Quando l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> è impostato su true e <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su <xref:System.ServiceModel.ConcurrencyMode.Single>, i messaggi inviati al servizio verranno elaborati in ordine. Nel frammento di codice seguente viene illustrato come impostare questi attributi.  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Se l'oggetto <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> è impostato su qualsiasi altro valore, viene generato un oggetto <xref:System.InvalidOperationException>.  
  
## <a name="see-also"></a>Vedere anche

- [Sessioni, istanze e concorrenza](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [Concorrenza](../../../../docs/framework/wcf/samples/concurrency.md)
