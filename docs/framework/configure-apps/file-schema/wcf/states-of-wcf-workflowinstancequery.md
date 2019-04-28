---
title: <states> di WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: fad6f9c8871f79e4a1e26c893eed86ba168f6d01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757950"
---
# <a name="states-of-wcf-workflowinstancequery"></a>\<stati > di WCF, \<workflowInstanceQuery >

Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.  
  
Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel> \<tracking>  
\<i profili >  
\<trackingProfile>  
\<flusso di lavoro >  
\<workflowInstanceQueries>  
\<workflowInstanceQuery>  
\<states>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <profiles>
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
|[\<states>](state-of-wcf-workflowinstancequery.md)|Stato sottoscritto dell'istanza del flusso di lavoro rilevata che si riferisce al momento della creazione del record.|  
  
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
|Operazione completata|L'istanza del flusso di lavoro viene completata.|  
|Eliminato|L'istanza del flusso di lavoro viene eliminata.|  
|Idle|L'istanza del flusso di lavoro è inattiva.|  
|Persisted|L'istanza del flusso di lavoro è persistente.|  
|Resumed|L'istanza del flusso di lavoro viene ripresa.|  
|Avviata|L'istanza del flusso di lavoro è avviata.|  
|UnhandledException|L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.|  
|Scaricato|L'istanza del flusso di lavoro viene scaricata.|  
|Annullato|L'istanza del flusso di lavoro viene annullata.|  
|Sospeso|L'istanza del flusso di lavoro è sospesa.|  
|Terminated|L'istanza del flusso di lavoro è terminata.|  
|Unsuspended|L'istanza del flusso di lavoro non è sospesa.|  
  
## <a name="example"></a>Esempio

La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
