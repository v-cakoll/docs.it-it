---
title: '&lt;memoryCache&gt; elemento (impostazioni della Cache)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 5862e696f084916f3359d185f42e84b2a2789a0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltmemorycachegt-element-cache-settings"></a>&lt;memoryCache&gt; elemento (impostazioni della Cache)
Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> . La classe <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> definisce un elemento [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) che è possibile usare per configurare la cache. In una singola applicazione possono essere usate più istanze della classe <xref:System.Runtime.Caching.MemoryCache> . Ogni elemento `memoryCache` nel file di configurazione può contenere le impostazioni per un'istanza denominata di <xref:System.Runtime.Caching.MemoryCache> .  
  
 \<configuration>  
\<Caching >  
\<memoryCache >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<memoryCache   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
< memoryCache />  
```  
  
## <a name="type"></a>Tipo  
 Classe<xref:System.Runtime.Caching.MemoryCache> .  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|La dimensione massima di memoria, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache>.|  
|`Name`|Nome della configurazione della cache.|  
|`PhysicalMemoryLimitPercentage`|Percentuale di memoria fisica utilizzabile dalla cache. Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .|  
|`PollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Il valore viene inserito nel formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Contiene tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
  
## <a name="remarks"></a>Note  
 La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione concreta della classe astratta <xref:System.Runtime.Caching.ObjectCache> . Alle istanze della classe <xref:System.Runtime.Caching.MemoryCache> possono essere fornite le informazioni di configurazione dei file di configurazione dell'applicazione. La sezione [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) della configurazione contiene una raccolta di configurazioni `namedCaches` .  
  
 Quando viene inizializzato un oggetto cache basato sulla memoria, esso tenta innanzitutto di trovare una voce `namedCaches` che corrisponde al nome nel parametro che viene passato al costruttore della cache in memoria. Se viene trovata una voce `namedCaches` , le informazioni di polling e di gestione della memoria vengono recuperate dal file di configurazione.  
  
 Il processo di inizializzazione determina quindi se è stato eseguito l'override di qualche voce di configurazione usando la raccolta facoltativa di coppie nome-valore delle informazioni di configurazione nel costruttore. Se viene passato uno qualsiasi dei seguenti valori nella raccolta di coppie nome-valore, questi valori eseguono l'override delle informazioni ottenute dal file di configurazione:  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come impostare il nome dell'oggetto <xref:System.Runtime.Caching.MemoryCache> sul nome dell'oggetto cache predefinito impostando l'attributo `name` "default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryLimitPercentage` sono impostati su zero. Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> . L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.  
  
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
 <xref:System.Runtime.Caching.MemoryCache>  
 [\<Caching > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)  
 [\<namedCaches > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
