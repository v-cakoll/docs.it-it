---
title: <workflowInstanceQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854734"
---
# <a name="workflowinstancequery-of-wcf"></a>\<> workflowInstanceQuery di WCF

Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.  
  
Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQuery**  
  
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
|[\<Stati >](states-of-wcf-workflowinstancequery.md)|Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<workflowInstanceQueries>](workflowinstancequeries-of-wcf.md)|Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.|  
  
## <a name="remarks"></a>Note  

L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
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
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
