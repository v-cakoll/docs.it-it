---
title: Elemento <system.runtime.caching> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91a97807d45d3cafdac0c0608dc9590533b185dc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663438"
---
# <a name="systemruntimecaching-element-cache-settings"></a>\<System. Runtime. Caching elemento > (impostazioni cache)

Fornisce la configurazione per l'implementazione predefinita in memoria <xref:System.Runtime.Caching.ObjectCache> tramite la voce `memoryCache` nel file di configurazione.  
  
 \<configuration>  
\<system.runtime.caching>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi

`None`  

### <a name="child-elements"></a>Elementi figlio

|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.|  
  
## <a name="remarks"></a>Note

Le classi in questo spazio dei nomi consentono di usare le funzionalità di memorizzazione nella cache come quelle in ASP.NET, ma senza una dipendenza sull'assembly `System.Web` . Per altre informazioni, vedere [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  La funzionalità di memorizzazione nella cache di output e <xref:System.Runtime.Caching> i tipi nello spazio dei nomi sono nuovi in .NET Framework 4.  
  
## <a name="example"></a>Esempio

L'esempio seguente illustra come configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> . L'esempio mostra come configurare un'istanza della voce `namedCaches` per la cache in memoria. Il nome della cache è impostato sul nome predefinito della voce della cache impostando l' `name` attributo su "default".  
  
Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero. Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> . L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.  
  
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

- [\<Elemento > memoryCache (impostazioni cache)](memorycache-element-cache-settings.md)
