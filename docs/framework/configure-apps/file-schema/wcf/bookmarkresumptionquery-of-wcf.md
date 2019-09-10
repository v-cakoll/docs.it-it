---
title: <bookmarkResumptionQuery>di WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 36d169b78e78692c7b45c75d5d375bddbba1c66f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850108"
---
# <a name="bookmarkresumptionquery-of-wcf"></a>\<> oggetto BookmarkResumptionQuery di WCF

Rappresenta una query usata per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di riassunzione dei segnalibri.  
  
Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<rilevamento >** ](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<profili >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di trackingProfile**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> flusso di lavoro**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> bookmarkResumptionQueries**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oggetto BookmarkResumptionQuery**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
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
|`name`|Stringa che specifica il nome del record di segnalibro da sottoscrivere.|  
  
### <a name="child-elements"></a>Elementi figlio

Nessuno.
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|Rappresenta una raccolta di query usate per rilevare la riassunzione di un segnalibro all'interno di un'istanza del flusso di lavoro.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
