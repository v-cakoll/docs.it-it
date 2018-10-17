---
title: '&lt;activityScheduledQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 35bcb0dc0c33d30eee566869579edb32f131f495
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374398"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a>&lt;activityScheduledQueries&gt; di WCF
Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.  
  
Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<rilevamento >  
\<i profili >  
\<trackingProfile>  
\<flusso di lavoro >  
\<activityScheduledQueries >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
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
|[\<activityScheduledQuery >](activityscheduledquery-of-wcf.md)|Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<flusso di lavoro >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.|  
  
## <a name="see-also"></a>Vedere anche  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
