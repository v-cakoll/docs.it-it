---
title: Utilizzo dell'annotazione nelle query
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 728408e744bc1eca62158fab1a7a17e985fe3b6c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69947291"
---
# <a name="using-annotation-in-queries"></a>Utilizzo dell'annotazione nelle query
Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione. È possibile, ad esempio, che si desideri contrassegnare più record di rilevamento in diversi flussi di lavoro con "mail server" = = "mail Server1". Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.  
  
## <a name="adding-annotations"></a>Aggiunta di annotazioni  
 Un'annotazione può essere aggiunta a una query di rilevamento come mostrato nell'esempio seguente.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento all'interno della configurazione o mediante codice.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
