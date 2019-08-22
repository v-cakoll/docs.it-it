---
title: Elemento <clear> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658857"
---
# <a name="clear-element-for-namedcaches"></a>\<Cancella > elemento per \<namedCaches >
Cancella tutte `namedCache` le voci della `namedCaches` raccolta per una cache in memoria.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 `None`  
  
### <a name="child-elements"></a>Elementi figlio  
 `None`  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.|  
  
## <a name="remarks"></a>Note  
 L' `clear` elemento Cancella tutte le `namedCache` voci della raccolta cache denominata per una cache in memoria. È possibile utilizzare l' `clear` elemento prima di utilizzare l' `add` elemento per aggiungere una nuova voce della cache denominata per assicurarsi che non vi siano altre cache denominate nella raccolta.  
  
## <a name="see-also"></a>Vedere anche

- [\<Elemento > namedCaches (impostazioni cache)](namedcaches-element-cache-settings.md)
