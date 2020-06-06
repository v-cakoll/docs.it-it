---
title: Elemento <add> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154505"
---
# <a name="add-element-for-namedcaches"></a>Elemento \<add> per \<namedCaches>
Aggiunge una `namedCache` voce alla `namedCaches` raccolta per una cache in memoria.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <add name="Default" />  
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
|`CacheMemoryLimitMegabytes`|Valore intero che specifica le dimensioni massime consentite (in megabyte) che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere. Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.|  
|`Name`|Nome della cache.|  
|`PhysicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache. Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.|  
|`PollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "HH: MM: SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
 `None`  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni di configurazione per le istanze denominate <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Commenti  
 L' `add` elemento aggiunge una voce alla `namedCaches` raccolta per una cache in memoria. È possibile utilizzare l'elemento [Clear](clear-element-for-namedcaches.md) prima di utilizzare l' `add` elemento per verificare che non siano presenti altre cache denominate nella raccolta. Questo elemento può essere utilizzato nel file Machine. config e nel file Web. config.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come definire le impostazioni per la `namedCache` voce predefinita della `namedCaches` raccolta per una cache in memoria.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- [\<namedCaches>Elemento (impostazioni cache)](namedcaches-element-cache-settings.md)
