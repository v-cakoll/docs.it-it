---
title: <activityStateQuery>di WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: ce7505896b9c5bb605bb0f67d735cb324f4fd493
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926904"
---
# <a name="activitystatequery-of-wcf"></a>\<> activityStateQuery di WCF

Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro. È possibile, ad esempio, tenere traccia di ogni volta che l'attività "Invia messaggio di posta elettronica" viene completata in un'istanza del flusso di lavoro. Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato. Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.  
  
Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).

\<system.serviceModel> \<tracking>  
\<profili > \<> TrackingProfile  
\<> flusso di lavoro  
\<activityStateQueries>  
\<activityStateQuery>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|activityName|Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Argomenti >](../windows-workflow-foundation/arguments.md)|Raccolta di argomenti associati a questa query di attività.|  
|[\<Stati >](../windows-workflow-foundation/states.md)|Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.|  
|[\<Stati >](../windows-workflow-foundation/states.md)|Raccolta di variabili associate a questa query di attività.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](../windows-workflow-foundation/faultpropagationquery.md)|Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre. La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.|  
  
## <a name="remarks"></a>Note

Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro. Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione. Per estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro, è possibile utilizzare gli [ \<argomenti >](../windows-workflow-foundation/arguments.md), [ \<gli Stati >](../windows-workflow-foundation/states.md) e [ \<gli Stati >](../windows-workflow-foundation/states.md) elementi. Nell'esempio seguente viene illustrata una query sullo stato dell'attività che estrae variabili e argomenti `Closed` quando viene generato il record di rilevamento dell'attività. Le variabili e gli argomenti possono essere estratti solo con un ActivityStateRecord e quindi sono sottoscritti all'interno di un profilo di rilevamento utilizzando [ \<activityStateQuery >](../windows-workflow-foundation/activitystatequery.md).  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
