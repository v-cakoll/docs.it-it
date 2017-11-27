---
title: '&lt;filtro&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86ae428eb29750a348c353a998116f8965b9bb41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltergt"></a>&lt;filtro&gt;

Definisce un filtro di routing che determina il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché gli eventuali dati o parametri di supporto necessari per il filtro.

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

| Attributo  | Descrizione |
| ---------- | ----------- |
| customType | Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro. Se `filterType` è impostato su `custom`, questo attributo contiene il nome completo del tipo di classe da creare.  `filterData`può inoltre contenere i valori da utilizzare durante la valutazione del filtro di tipo personalizzato. |
| filterData | Stringa contenente i dati del filtro. Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Stringa contenente i tipo di filtro. L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Stringa contenente il nome univoco di questo elemento di filtro. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [\<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo. |

## <a name="see-also"></a>Vedere anche

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
