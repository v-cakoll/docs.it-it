---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269575"
---
# <a name="namespacetable"></a>\<namespaceTable>

Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.

**\<system.serviceModel>**   
&nbsp;&nbsp;**\<routing>**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

nessuno

### <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [**\<filter>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath. |

### <a name="parent-elements"></a>Elementi padre

|     | Descrizione |
| --- | ----------- |
| [**\<routing>**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
