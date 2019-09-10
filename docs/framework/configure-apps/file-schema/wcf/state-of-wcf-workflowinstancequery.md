---
title: <state>di WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854958"
---
# <a name="state-of-wcf-workflowinstancequery"></a>\<> di stato di WCF \<, workflowInstanceQuery >
Rappresenta una raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.  
  
 Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Stati >** ](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di stato**  
  
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

|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Stringa che specifica uno stato sottoscritto dell'istanza del flusso di lavoro rilevata quando viene creato il record di rilevamento.|  
  
### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Stati >](states-of-wcf-workflowinstancequery.md)|Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.|  
  
## <a name="remarks"></a>Note  

I record restituiti vengono filtrati in base agli stati di questa raccolta.  
  
Nella tabella seguente sono descritti i valori di stato possibili:
  
|Stato|Descrizione|  
|-----------|-----------------|  
|Aborted|L'istanza del flusso di lavoro viene interrotta.|  
|Operazione completata|L'istanza del flusso di lavoro viene completata.|  
|Eliminato|L'istanza del flusso di lavoro viene eliminata.|  
|Idle|L'istanza del flusso di lavoro è inattiva.|  
|Persisted|L'istanza del flusso di lavoro è persistente.|  
|Resumed|L'istanza del flusso di lavoro viene ripresa.|  
|Started|L'istanza del flusso di lavoro è avviata.|  
|UnhandledException|L'istanza del flusso di lavoro ha rilevato un'eccezione non gestita.|  
|Scaricato|L'istanza del flusso di lavoro viene scaricata.|  
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
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
