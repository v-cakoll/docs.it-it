---
title: '&lt;Stati&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fe02106d8d7f70cb328214c7e464d80a41b75528
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltstatesgt"></a>&lt;Stati&gt;
Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.  
  
 Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<rilevamento >  
\<trackingProfile>  
\<flusso di lavoro >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<stati >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
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
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<stato >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.|  
  
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
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
