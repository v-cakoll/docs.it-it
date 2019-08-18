---
title: <add> di <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 32eff2e7bfdf1aee4c7d37a0e06166afba3cb398
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566743"
---
# <a name="add-of-namespacetable"></a>\<aggiungere > di \<namespaceTable >
Rappresenta un elemento di configurazione contenente uno spazio dei nomi da anteporre al mapping che può quindi essere usato nei filtri XPath per il routing.  
  
 \<system.serviceModel>  
\<routing>  
\<namespaceTable>  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|namespace|Stringa contenente lo spazio dei nomi.|  
|prefix|Stringa contenente il prefisso per questo spazio dei nomi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namespaceTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
