---
title: <filters> di <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855245"
---
# <a name="filters-of-routing"></a>\<Filtra > di \<> di routing

Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo.

[ **\<system.serviceModel>** ](system-servicemodel.md)\
&nbsp;&nbsp;[ **\<routing>** ](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**  
  
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
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

Nessuna

### <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<filter>** ](filter.md) | Contiene un filtro di routing che determina il tipo di Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) che verrà utilizzato durante la valutazione di messaggi in arrivo. |

### <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [ **\<routing>** ](routing.md) | Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
