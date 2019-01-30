---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278785"
---
# <a name="filter"></a>\<filter>

Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, come i dati di supporto o i parametri richiesti dal filtro.

\<system.serviceModel> \<routing> \<filters> \<filter>
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

| Attributo  | Descrizione |
| ---------- | ----------- |
| customType | Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro. Se `filterType` è impostata su `custom`, questo attributo contiene il nome del tipo completo della classe da creare.  `filterData` può inoltre contenere valori da utilizzare durante la valutazione del filtro di tipo personalizzato. |
| filterData | Stringa contenente i dati del filtro. Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Stringa contenente i tipo di filtro. L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Stringa contenente il nome univoco di questo elemento di filtro. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in ingresso. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
