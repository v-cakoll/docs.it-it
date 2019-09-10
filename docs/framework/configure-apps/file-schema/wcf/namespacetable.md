---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855104"
---
# <a name="namespacetable"></a>\<namespaceTable>

Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> namespaceTable**  
  
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

Nessuna

### <a name="child-elements"></a>Elementi figlio

|     | Descrizione |
| --- | ----------- |
| [ **\<filter>** ](filter.md) | Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath. |

### <a name="parent-elements"></a>Elementi padre

|     | DESCRIZIONE |
| --- | ----------- |
| [ **\<routing>** ](routing.md) | Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro. |

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
