---
title: '&lt;namedCaches&gt; (impostazioni Cache)'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a824e958a2b75b28aa66a15212e0276d6c127739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536529"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; (impostazioni Cache)
Specifica una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze. Il <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno o più `namedCaches` gli elementi del file di configurazione.  
  
 \<configuration>  
\< system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
  
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
|`cacheMemoryLimitMegabytes`|Valore intero che specifica la dimensione massima consentita, in megabyte, che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0, che significa che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate per impostazione predefinita.|  
|`name`|Nome della cache.|  
|`physicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer fisicamente installati che può essere utilizzata dalla cache. Il valore predefinito è 0, che significa che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate per impostazione predefinita.|  
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
 La sezione di configurazione della memoria cache del file Web. config deve contenere `add`, `remove`, e `clear` gli attributi per il `namedCaches` raccolta. Ciascuna `namedCaches` voce è identificata dal `name` attributo.  
  
 È possibile recuperare le istanze di voci della cache di memoria facendo le informazioni nei file di configurazione dell'applicazione. Per impostazione predefinita, solo l'istanza di cache predefinita include una voce nel file di configurazione. L'istanza di cache predefinita è l'istanza che viene restituito dal <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.  
  
 Se si imposta l'attributo name su "default", l'elemento Usa l'istanza di cache di memoria predefinita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il nome della cache per il nome della voce della cache predefinita impostando la `name` attributo "default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero. L'impostazione di questi attributi a zero indica che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate. L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria in percentuale e assoluti ogni due minuti.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [\<memoryCache > (impostazioni Cache)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
