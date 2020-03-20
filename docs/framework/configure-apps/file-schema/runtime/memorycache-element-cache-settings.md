---
title: Elemento <memoryCache> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 94c21e0408b7616bf0c8a24267b72bfa7cc3aaa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153984"
---
# <a name="memorycache-element-cache-settings"></a>\<Elemento> memoryCache (impostazioni cache)
Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> . La classe <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> definisce un elemento [memoryCache](memorycache-element-cache-settings.md) che è possibile usare per configurare la cache. In una singola applicazione possono essere usate più istanze della classe <xref:System.Runtime.Caching.MemoryCache> . Ogni elemento `memoryCache` nel file di configurazione può contenere le impostazioni per un'istanza denominata di <xref:System.Runtime.Caching.MemoryCache> .  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>memoryCache**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a>Type  
 Classe<xref:System.Runtime.Caching.MemoryCache> .  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|La dimensione massima di memoria, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .|  
|`Name`|Nome della configurazione della cache.|  
|`PhysicalMemoryLimitPercentage`|Percentuale di memoria fisica utilizzabile dalla cache. Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .|  
|`PollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Il valore viene inserito nel formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>namedCaches](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di configurazione](../configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione utilizzato da Common Language Runtime e dalle applicazioni .NET Framework.|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni incorporate in .NET Framework.|  
  
## <a name="remarks"></a>Osservazioni  
 La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione concreta della classe astratta <xref:System.Runtime.Caching.ObjectCache> . Alle istanze della classe <xref:System.Runtime.Caching.MemoryCache> possono essere fornite le informazioni di configurazione dei file di configurazione dell'applicazione. La sezione [memoryCache](memorycache-element-cache-settings.md) della configurazione contiene una raccolta di configurazioni `namedCaches` .  
  
 Quando viene inizializzato un oggetto cache basato sulla memoria, esso tenta innanzitutto di trovare una voce `namedCaches` che corrisponde al nome nel parametro che viene passato al costruttore della cache in memoria. Se viene trovata una voce `namedCaches` , le informazioni di polling e di gestione della memoria vengono recuperate dal file di configurazione.  
  
 Il processo di inizializzazione determina quindi se è stato eseguito l'override di qualche voce di configurazione usando la raccolta facoltativa di coppie nome-valore delle informazioni di configurazione nel costruttore. Se viene passato uno qualsiasi dei seguenti valori nella raccolta di coppie nome-valore, questi valori eseguono l'override delle informazioni ottenute dal file di configurazione:  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come <xref:System.Runtime.Caching.MemoryCache> impostare il nome dell'oggetto sul nome predefinito dell'oggetto cache impostando l'attributo `name` su "Default".  
  
 Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryLimitPercentage` sono impostati su zero. Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> . L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Caching.MemoryCache>
- [\<system.runtime.caching>elemento (Impostazioni cache)](system-runtime-caching-element-cache-settings.md)
- [\<Elemento> namedCaches (impostazioni cache)](namedcaches-element-cache-settings.md)
