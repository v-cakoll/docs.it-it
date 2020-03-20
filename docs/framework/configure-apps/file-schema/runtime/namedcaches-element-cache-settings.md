---
title: Elemento <namedCaches> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153958"
---
# <a name="namedcaches-element-cache-settings"></a>\<Elemento> namedCaches (impostazioni cache)
Specifica una raccolta di impostazioni <xref:System.Runtime.Caching.MemoryCache> di configurazione per le istanze denominate. La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta `namedCaches` di impostazioni di configurazione da uno o più elementi del file di configurazione.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>memoryCache**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>namedCaches**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Valore intero che specifica la dimensione massima consentita, in megabyte, fino a cui può aumentare un'istanza di un <xref:System.Runtime.Caching.MemoryCache> oggetto . Il valore predefinito è 0, il che significa che <xref:System.Runtime.Caching.MemoryCache> le euristiche di ridimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`name`|Nome della cache.|  
|`physicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache. Il valore predefinito è 0, il che significa che <xref:System.Runtime.Caching.MemoryCache> le euristiche di ridimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`pollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<aggiungere>](add-element-for-namedcaches.md)|Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.|  
|[\<>chiari](clear-element-for-namedcaches.md)|Cancella la raccolta `namedCaches` per una cache in memoria.|  
|[\<rimuovere>](remove-element-for-namedcaches.md)|Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di configurazione](../configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione utilizzato da Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<>memoryCache](memorycache-element-cache-settings.md)|Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni incorporate in .NET Framework.|  
  
## <a name="remarks"></a>Osservazioni  
 La sezione di configurazione della cache di `add` `remove`memoria `clear` del file `namedCaches` Web.config può contenere gli attributi , e per l'insieme. Ogni `namedCaches` voce è identificata `name` in modo univoco dall'attributo.  
  
 È possibile recuperare le istanze delle voci della cache di memoria facendo riferimento alle informazioni nei file di configurazione dell'applicazione. Per impostazione predefinita, solo l'istanza della cache predefinita ha una voce nel file di configurazione. L'istanza della cache predefinita è l'istanza restituita dalla <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.  
  
 Se si imposta l'attributo name su "default", l'elemento utilizza l'istanza predefinita della cache di memoria.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il nome della `name` cache sul nome della voce della cache predefinito impostando l'attributo su "default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero. L'impostazione di questi attributi su zero significa <xref:System.Runtime.Caching.MemoryCache> che vengono utilizzate le euristiche di ridimensionamento automatico della classe. L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria assoluti e basati sulla percentuale ogni due minuti.  
  
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

- [\<Elemento> memoryCache (impostazioni cache)](memorycache-element-cache-settings.md)
