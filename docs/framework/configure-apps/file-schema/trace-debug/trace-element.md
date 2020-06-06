---
title: <trace> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153166"
---
# <a name="trace-element"></a>\<trace> Elemento
Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`autoflush`|Attributo facoltativo.<br /><br /> Specifica se i listener di traccia scaricano automaticamente il buffer di output dopo ogni operazione di scrittura.|  
|`indentsize`|Attributo facoltativo.<br /><br /> Specifica il numero di spazi da rientrare.|  
|`useGlobalLock`|Attributo facoltativo.<br /><br /> Indica se deve essere utilizzato il blocco globale.|  
  
## <a name="autoflush-attribute"></a>AutoFlush (attributo)  
  
|Valore|Description|  
|-----------|-----------------|  
|`false`|Non Scarica automaticamente il buffer di output. Questo è il valore predefinito.|  
|`true`|Scarica automaticamente il buffer di output.|  
  
## <a name="usegloballock-attribute"></a>Attributo useGlobalLock  
  
|Valore|Description|  
|-----------|-----------------|  
|`false`|Non utilizza il blocco globale se il listener è thread-safe. in caso contrario, utilizza il blocco globale.|  
|`true`|Usa il blocco globale indipendentemente dal fatto che il listener sia thread-safe. Questo è il valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|Specifica un listener che raccoglie, archivia e instrada i messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `<trace>` elemento per aggiungere il listener `MyListener` alla `Listeners` raccolta. `MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file. L' `useGlobalLock` attributo è impostato su `false` , che impedisce l'utilizzo del blocco globale se il listener di traccia è thread-safe. L' `autoflush` attributo è impostato su `true` , che fa sì che il listener di traccia scriva nel file, indipendentemente dal fatto che il <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> metodo venga chiamato. L' `indentsize` attributo è impostato su 0 (zero), che fa sì che il listener rientri zero spazi quando <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> viene chiamato il metodo.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
