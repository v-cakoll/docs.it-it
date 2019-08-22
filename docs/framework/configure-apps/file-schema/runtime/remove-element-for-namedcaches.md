---
title: Elemento <remove> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663480"
---
# <a name="remove-element-for-namedcaches"></a>\<Rimuovi elemento > per \<namedCaches >
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
  
## <a name="type"></a>Type  
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
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.|  
  
## <a name="remarks"></a>Note  
 L' `remove` elemento rimuove una `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.  
  
## <a name="see-also"></a>Vedere anche

- [\<Elemento > namedCaches (impostazioni cache)](namedcaches-element-cache-settings.md)
