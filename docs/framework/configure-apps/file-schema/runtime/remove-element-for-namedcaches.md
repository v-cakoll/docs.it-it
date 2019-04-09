---
title: <remove> (elemento) per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229771"
---
# <a name="remove-element-for-namedcaches"></a>\<rimuovere > (elemento) per \<namedCaches >
Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<remove>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `None`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 `None`  
  
### <a name="child-elements"></a>Elementi figlio  
 `None`  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.|  
  
## <a name="remarks"></a>Note  
 Il `remove` elemento consente di rimuovere un `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.  
  
## <a name="see-also"></a>Vedere anche

- [\<namedCaches > (impostazioni Cache)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
