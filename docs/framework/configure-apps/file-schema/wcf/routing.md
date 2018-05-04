---
title: '&lt;Routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a>&lt;Routing&gt;

Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione a tabelle inviare messaggi quando un filtro trovata una corrispondenza.

[**\<System. ServiceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<routing >**

## <a name="syntax"></a>Sintassi

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

Nessuno

### <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<i filtri >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Contiene un set di filtri di routing che determinano che il tipo di MessageFilter di Windows Communication Foundation (WCF) verrà utilizzato durante la valutazione di messaggi in arrivo. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro. |

### <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| **\<System. ServiceModel >** | Elemento radice di tutti gli elementi di configurazione WCF. |

## <a name="see-also"></a>Vedere anche

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
