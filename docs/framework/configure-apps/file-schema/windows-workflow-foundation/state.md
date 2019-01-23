---
title: '&lt;state&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 8e381671d9282218a4e5bf0ae979bec79c7cfe78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523051"
---
# <a name="ltstategt"></a>&lt;state&gt;
Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.  
  
 Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<tracking>  
\<trackingProfile>  
\<flusso di lavoro >  
\<workflowInstanceQueries>  
\<workflowInstanceQuery>  
\<states>  
\<state>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.|  
  
## <a name="remarks"></a>Note  
 I record restituiti vengono filtrati in base agli stati di questa raccolta.  
  
 I valori possibili dello stato sono descritti nella tabella seguente.  
  
|Stato|Descrizione|  
|-----------|-----------------|  
|Aborted|L'istanza del flusso di lavoro viene interrotta.|  
|Completata|L'istanza del flusso di lavoro viene completata.|  
|Eliminato|L'istanza del flusso di lavoro viene eliminata.|  
|Idle|L'istanza del flusso di lavoro è inattiva.|  
|Persisted|L'istanza del flusso di lavoro è persistente.|  
|Resumed|L'istanza del flusso di lavoro viene ripresa.|  
|Started|L'istanza del flusso di lavoro è avviata.|  
|UnhandledException|L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.|  
|Unloaded|L'istanza del flusso di lavoro viene scaricata.|  
|Annullato|L'istanza del flusso di lavoro viene annullata.|  
|Suspended|L'istanza del flusso di lavoro è sospesa.|  
|Terminated|L'istanza del flusso di lavoro è terminata.|  
|Unsuspended|L'istanza del flusso di lavoro non è sospesa.|  
  
## <a name="example"></a>Esempio  
 La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
