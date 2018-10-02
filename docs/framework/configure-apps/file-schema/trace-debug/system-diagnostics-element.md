---
title: '&lt;System. Diagnostics&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 35fe167beb53c27aa511e08507415a26b1749ca2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029438"
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System. Diagnostics&gt; elemento
Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.|  
|[\<performanceCounters>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.|  
|[\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia. I listener identificati come listener condivisi possono essere aggiunti alle origini o delle tracce in base al nome.|  
|[\<sources>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Specifica le origini di traccia che avviano i messaggi di traccia.|  
|[\<switches>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Contiene le opzioni di traccia e i livelli in cui vengono impostate le opzioni di traccia.|  
|[\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia all'interno di  **\<System. Diagnostics >** elemento. Il `General` opzione di traccia è impostato sul <xref:System.Diagnostics.TraceLevel> livello. Il listener di traccia `myListener` crea un file denominato `MyListener.log` e scrive l'output del file.  
  
> [!NOTE]
>  In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione, Ad esempio, è possibile specificare `true` per un <xref:System.Diagnostics.BooleanSwitch> o usare il testo che rappresenta un valore di enumerazione, ad esempio `Error` per un <xref:System.Diagnostics.TraceSwitch>. La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
