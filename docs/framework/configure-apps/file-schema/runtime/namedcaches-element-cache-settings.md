---
title: '&lt;namedCaches&gt; elemento (impostazioni della Cache)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f4c4bd9901b053c96a260435c34ffa3ddd2c7283
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; elemento (impostazioni della Cache)
Specifica una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze. Il <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno o più `namedCaches` elementi del file di configurazione.  
  
 \<configuration>  
\<Caching >  
\<memoryCache >  
\<namedCaches >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `None`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Valore intero che specifica la dimensione massima consentita, in megabyte, che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0, il che significa che l'euristica di ridimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzati per impostazione predefinita.|  
|`name`|Nome della cache.|  
|`physicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria installata fisicamente i computer che può essere utilizzata dalla cache. Il valore predefinito è 0, il che significa che l'euristica di ridimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzati per impostazione predefinita.|  
|`pollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "Hh".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Cancella la raccolta `namedCaches` per una cache in memoria.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Note  
 La sezione di configurazione della memoria cache del file Web. config può contenere `add`, `remove`, e `clear` gli attributi per il `namedCaches` insieme. Ogni `namedCaches` voce viene identificata in modo univoco dal `name` attributo.  
  
 È possibile recuperare le istanze di voci della cache di memoria facendo riferimento alle informazioni nei file di configurazione dell'applicazione. Per impostazione predefinita, solo l'istanza di cache predefinita ha una voce nel file di configurazione. L'istanza di cache predefinita è l'istanza restituita dal <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.  
  
 Se si imposta l'attributo name per "default", l'elemento Usa l'istanza di cache di memoria predefinita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il nome della cache per il nome della voce della cache predefinita impostando la `name` attributo "default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero. L'impostazione di questi attributi su zero significa che l'euristica di ridimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzati. L'implementazione della cache confronta il carico di memoria corrente limiti di memoria in percentuale e assoluti ogni due minuti.  
  
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
 [\<memoryCache > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
