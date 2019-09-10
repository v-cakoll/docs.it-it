---
title: <customTrackingQueries>di WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855442"
---
# <a name="customtrackingqueries-of-wcf"></a>\<> customTrackingQueries di WCF

Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.  
  
Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQueries**  

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
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|Query usata per rilevare gli eventi definiti nelle attività del codice.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
