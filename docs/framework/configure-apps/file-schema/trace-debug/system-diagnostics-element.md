---
title: <elemento> system.diagnostics
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153207"
---
# <a name="systemdiagnostics-element"></a>\<Elemento> system.diagnostics
Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;**\<>system.diagnostics**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<affermare>](assert-element.md)|Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.|  
|[\<performanceContatori>](performancecounters-element.md)|Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.|  
|[\<>sharedListeners](sharedlisteners-element.md)|Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia. I listener identificati come listener condivisi possono essere aggiunti alle origini o alle tracce in base al nome.|  
|[\<fonti>](sources-element.md)|Specifica le origini di traccia che avviano i messaggi di traccia.|  
|[\<interruttori>](switches-element.md)|Contiene le opzioni di traccia e i livelli in cui sono impostate le opzioni di traccia.|  
|[\<>traccia](trace-element.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia all'interno dell'elemento ** \<>system.diagnostics.** L'opzione `General` di traccia <xref:System.Diagnostics.TraceLevel> è impostata sul livello. Il listener `myListener` di traccia `MyListener.log` crea un file chiamato e scrive l'output nel file.  
  
> [!NOTE]
> In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione, Ad esempio, è `true` possibile <xref:System.Diagnostics.BooleanSwitch> specificare per un oggetto o `Error` utilizzare <xref:System.Diagnostics.TraceSwitch>il testo che rappresenta un valore di enumerazione, ad esempio per un oggetto . La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.  
  
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

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Schema delle impostazioni di traccia e debug](index.md)
