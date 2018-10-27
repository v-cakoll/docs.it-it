---
title: '&lt;customTrackingQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 060e2b5c8efd51f6245a39bd9562a69f0111fd41
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50038786"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a>&lt;customTrackingQueries&gt; di WCF

Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.  
  
 Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).
  
\<system.serviceModel>  
\<rilevamento >  
\<i profili >  
\<trackingProfile>  
\<flusso di lavoro >  
\<customTrackingQueries >  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
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
|[\<customTrackingQuery >](customtrackingquery-of-wcf.md)|Query usata per rilevare gli eventi definiti nelle attività del codice.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<flusso di lavoro >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
