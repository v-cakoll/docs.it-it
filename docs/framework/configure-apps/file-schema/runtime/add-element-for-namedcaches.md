---
title: '&lt;aggiungere&gt; elemento per &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0000e92c89920b05e0ffc93fab58fb0bd6ea6b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;aggiungere&gt; elemento per &lt;namedCaches&gt;
Aggiunge un `namedCache` voce per il `namedCaches` insieme per una cache in memoria.  
  
 \<Caching >  
\<memoryCache >  
\<namedCaches >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `None`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Valore intero che specifica la dimensione massima consentita (in megabyte) che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0, il che significa che il <xref:System.Runtime.Caching.MemoryCache> euristiche di dimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`Name`|Nome della cache.|  
|`PhysicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria installata fisicamente i computer che può essere utilizzata dalla cache. Il valore predefinito è 0, il che significa che il <xref:System.Runtime.Caching.MemoryCache> euristiche di dimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`PollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "Hh".|  
  
### <a name="child-elements"></a>Elementi figlio  
 `None`  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.|  
  
## <a name="remarks"></a>Note  
 Il `add` elemento aggiunge una voce per il `namedCaches` insieme per una cache in memoria. È possibile utilizzare il [deselezionare](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) elemento prima di utilizzare il `add` elemento per essere certi che vi siano altre cache denominate nella raccolta. Questo elemento può essere usato nel file Machine. config e nel file Web. config.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come definire le impostazioni per il valore predefinito `namedCache` voce per il `namedCaches` insieme per una cache in memoria.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [\<namedCaches > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
