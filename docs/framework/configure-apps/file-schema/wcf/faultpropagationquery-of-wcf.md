---
title: <faultPropagationQuery>di WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 6ba6478ca500c0a8ef150966a97898f8743ffdf8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925625"
---
# <a name="faultpropagationquery-of-wcf"></a>\<> oggetto FaultPropagationQuery di WCF

Rappresenta una query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.  Questo evento si verifica ogni volta che un FaultHandler elabora un errore. È necessario usare tale query per rilevare la gestione degli errori che si verificano all'interno di un'attività. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di propagazione degli errori.

Per ulteriori informazioni sulle query del profilo di rilevamento, vedere [profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md).

\<system.serviceModel>\
\<rilevamento > \
\<profili > \
\<trackingProfile > \
\<> flusso di lavoro \
\<faultPropagationQueries>\
\<faultPropagationQuery>

## <a name="syntax"></a>Sintassi

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
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
|`faultSourceActivityName`|Stringa che specifica il nome dell'attività del gestore errori che ha propagato l'errore. Il valore predefinito \*è, che indica che i record di propagazione degli errori vengono restituiti per tutte le attività.|
|`faultHandlerActivityName`|Stringa che specifica il nome dell'attività che ha originato l'errore.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|DESCRIZIONE|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|Rappresenta un elenco di elementi di configurazione utilizzati per rilevare la gestione degli errori che si verificano all'interno di un'attività.  Questo evento si verifica ogni volta che un FaultHandler elabora un errore.|

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Rilevamento e analisi del flusso di lavoro](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Profili di rilevamento](../../../windows-workflow-foundation/tracking-profiles.md)
