---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151910"
---
# \<tracking>
Rappresenta una sezione di configurazione per la definizione delle impostazioni di rilevamento di un servizio flusso di lavoro.  
  
 Per ulteriori informazioni sul rilevamento del flusso di lavoro e sulla relativa configurazione, vedere [rilevamento e traccia del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) e [configurazione del rilevamento per un flusso di lavoro](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String"
             profileName="String"
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<participants>](participants.md)|Raccolta di elementi di configurazione che definiscono partecipanti che sottoscrivono record di rilevamento. I partecipanti del rilevamento contengono la logica per elaborare il payload dai record di rilevamento, ad esempio possono scegliere di scrivere in un file.|  
|[\<trackingProfile>](trackingprofile.md)|Profilo di rilevamento che consente di filtrare i record di rilevamento generati da un'istanza del flusso di lavoro.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|system.ServiceModel|Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.|  
  
## <a name="remarks"></a>Commenti  
 Il rilevamento consente di esaminare l'esecuzione di un flusso di lavoro. L'infrastruttura di rilevamento del flusso di lavoro instrumenta un flusso di lavoro per generare record che riflettono gli eventi principali che si verificano durante l'esecuzione. Vengono ad esempio generati record di rilevamento quando viene avviata o completata un'istanza del flusso di lavoro. Il rilevamento consente inoltre di estrarre dati aziendali rilevanti associati alle variabili del flusso di lavoro. Se, ad esempio, il flusso di lavoro rappresenta un sistema di elaborazione degli ordini, è possibile estrarre l'ID dell'ordine insieme al record di rilevamento. In generale, l'abilitazione del rilevamento WF semplifica la diagnostica o l'analisi aziendale dell'esecuzione di un flusso di lavoro.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
