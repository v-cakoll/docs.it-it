---
title: Elemento <namedCaches> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 9cedd462aa539745ddab844dff158912914cb024
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663572"
---
# <a name="namedcaches-element-cache-settings"></a>\<Elemento > namedCaches (impostazioni cache)
Specifica una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate. La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno `namedCaches` o più elementi del file di configurazione.  
  
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
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Valore intero che specifica le dimensioni massime consentite, in megabyte, che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> oggetto può raggiungere. Il valore predefinito è 0, che indica che per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe.|  
|`name`|Nome della cache.|  
|`physicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache. Il valore predefinito è 0, che indica che per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe.|  
|`pollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "HH: MM: SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.|  
|[\<clear>](clear-element-for-namedcaches.md)|Cancella la raccolta `namedCaches` per una cache in memoria.|  
|[\<remove>](remove-element-for-namedcaches.md)|Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Note  
 La sezione di configurazione della cache in memoria del file Web. config `add`può `remove`contenere gli `clear` attributi, e `namedCaches` per la raccolta. Ogni `namedCaches` voce viene identificata `name` in modo univoco dall'attributo.  
  
 È possibile recuperare le istanze delle voci della cache di memoria facendo riferimento alle informazioni nei file di configurazione dell'applicazione. Per impostazione predefinita, solo l'istanza della cache predefinita include una voce nel file di configurazione. L'istanza della cache predefinita è l'istanza restituita dalla <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.  
  
 Se si imposta l'attributo Name su "default", l'elemento utilizza l'istanza della cache di memoria predefinita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il nome della cache sul nome della voce della cache predefinita impostando l' `name` attributo su "default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero. L'impostazione di questi attributi su zero indica che vengono utilizzate le euristiche <xref:System.Runtime.Caching.MemoryCache> di dimensionamento automatico della classe. L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria assoluti e in percentuale ogni due minuti.  
  
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

- [\<Elemento > memoryCache (impostazioni cache)](memorycache-element-cache-settings.md)
