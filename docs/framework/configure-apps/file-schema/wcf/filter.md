---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918888"
---
# <a name="filter"></a>\<Filtra >

Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché qualsiasi dato o parametro di supporto richiesto dal filtro.

\<System. ServiceModel > \<routing > \<filtri > \<filtro >
  
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

| Attributo  | DESCRIZIONE |
| ---------- | ----------- |
| customType | Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro. Se `filterType` è impostato su `custom`, questo attributo contiene il nome completo del tipo della classe da creare.  `filterData`può contenere anche valori da usare durante la valutazione del filtro di tipo personalizzato. |
| filterData | Stringa contenente i dati del filtro. Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Stringa contenente i tipo di filtro. L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Stringa contenente il nome univoco di questo elemento di filtro. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [\<routing>](routing.md) | Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) da utilizzare durante la valutazione di messaggi in arrivo. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
