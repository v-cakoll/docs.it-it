---
title: '&lt;filter&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 9fae9a599299fdd8cf1e996593514fc0ef38b6ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645509"
---
# <a name="ltfiltergt"></a>&lt;filter&gt;

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
