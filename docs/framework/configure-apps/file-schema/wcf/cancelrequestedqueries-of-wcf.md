---
title: '&lt;cancelRequestedQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 40fbcafd641e93be6ba21635f4f6e6428be62c12
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373322"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a>&lt;cancelRequestedQueries&gt; di WCF
Rappresenta una raccolta di query usate per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre. La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.  
  
Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<rilevamento >  
\<i profili > \<trackingProfile >  
\<flusso di lavoro >  
\<cancelRequestedQueries>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a>Attributi ed elementi  

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi

Nessuno.
  
### <a name="child-elements"></a>Elementi figlio
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|Query usata per rilevare richieste di annullamento di un'attività figlio da parte dell'attività padre.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<flusso di lavoro >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
