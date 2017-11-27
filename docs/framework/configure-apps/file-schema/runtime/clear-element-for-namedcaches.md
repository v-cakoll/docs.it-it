---
title: '&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0819141b2135a2de99a2801a1888f7b0e1cd19fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a>&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;
Cancella tutti `namedCache` voci di `namedCaches` insieme per una cache in memoria.  
  
 \<Caching >  
\<memoryCache >  
\<namedCaches >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
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
 Il `clear` elemento cancella tutti `namedCache` voci nella raccolta di cache denominata per una cache in memoria. È possibile utilizzare il `clear` elemento prima di utilizzare il `add` elemento per aggiungere una nuova voce di cache denominata per essere certi che vi siano altre cache denominate nella raccolta.  
  
## <a name="see-also"></a>Vedere anche  
 [\<namedCaches > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
