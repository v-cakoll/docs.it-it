---
title: Utilizzo dell'annotazione nelle query
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208644"
---
# <a name="using-annotation-in-queries"></a>Utilizzo dell'annotazione nelle query
Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione. Ad esempio, è possibile diversi record di rilevamento in diversi flussi di lavoro deve essere contrassegnato con "Mail Server" = = "Mail Server1". Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.  
  
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
>  Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento all'interno della configurazione o mediante codice.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<i partecipanti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [Rilevamento e traccia del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
