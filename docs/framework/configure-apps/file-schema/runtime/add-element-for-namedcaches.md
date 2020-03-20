---
title: Elemento <add> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154505"
---
# <a name="add-element-for-namedcaches"></a>\<Add> \<Element per namedCaches>
Aggiunge `namedCache` una voce `namedCaches` alla raccolta per una cache di memoria.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>memoryCache**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>namedCaches**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Valore intero che specifica la dimensione massima consentita (in <xref:System.Runtime.Caching.MemoryCache> megabyte) fino a cui può aumentare un'istanza. Il valore predefinito è 0, <xref:System.Runtime.Caching.MemoryCache> il che significa che le euristiche di ridimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`Name`|Nome della cache.|  
|`PhysicalMemoryLimitPercentage`|Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache. Il valore predefinito è 0, <xref:System.Runtime.Caching.MemoryCache> il che significa che le euristiche di ridimensionamento automatico della classe vengono utilizzate per impostazione predefinita.|  
|`PollingInterval`|Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache. Questo valore viene immesso nel formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementi figlio  
 `None`  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>namedCaches](namedcaches-element-cache-settings.md)|Contiene una raccolta di impostazioni <xref:System.Runtime.Caching.MemoryCache> di configurazione per le istanze denominate.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `add` aggiunge una `namedCaches` voce alla raccolta per una cache di memoria. È possibile [clear](clear-element-for-namedcaches.md) utilizzare l'elemento `add` clear prima di utilizzare l'elemento per essere certi che non siano presenti altre cache denominate nella raccolta. Questo elemento può essere utilizzato nel file machine.config e nel file Web.config.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come `namedCache` definire `namedCaches` le impostazioni per la voce predefinita nella raccolta per una cache di memoria.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [\<Elemento> namedCaches (impostazioni cache)](namedcaches-element-cache-settings.md)
