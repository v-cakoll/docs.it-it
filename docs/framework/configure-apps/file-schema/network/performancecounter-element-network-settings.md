---
title: Elemento <performanceCounter> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 58a2bf5118a3a2cd9c33301eca5dcc751c2351bf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283086"
---
# <a name="performancecounter-element-network-settings"></a>Elemento \<performanceCounter > (impostazioni di rete)
Abilita o Disabilita i contatori delle prestazioni di rete.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**Impostazioni**](settings-element-network-settings.md)\<>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PerformanceCounters**\<

## <a name="syntax"></a>Sintassi  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|description|  
|---------------|-----------------|  
|`enabled`|Specifica se i contatori delle prestazioni di rete sono abilitati. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|description|  
|-------------|-----------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
 I contatori delle prestazioni della rete devono essere abilitati nel file di configurazione da usare. Tutti i contatori delle prestazioni della rete vengono abilitati o disabilitati con una singola impostazione nel file di configurazione. Non è possibile abilitare o disabilitare singoli contatori delle prestazioni della rete. Per ulteriori informazioni sui contatori delle prestazioni di rete specifici, vedere [contatori delle prestazioni di rete](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).  
  
 Il valore predefinito è che i contatori delle prestazioni di rete sono disabilitati.  
  
 È possibile utilizzare la proprietà <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> per ottenere il valore corrente dell'attributo **Enabled** dai file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il <xref:System.Net> e gli spazi dei nomi correlati per abilitare i contatori delle prestazioni di rete.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
- [Contatori delle prestazioni di rete](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
