---
title: '&lt;deselezionare&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b2739cc5eaa6a1e43c06849e1b00f7ac8bd531e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;deselezionare&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;
Cancella la raccolta `Listeners` per una traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
\<traccia >  
\<listener >  
\<Deselezionare >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener di raccolgano, archiviano e indirizzare i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
  
## <a name="remarks"></a>Note  
 Il `<clear>` elemento rimuove tutti i listener dal `Listeners` insieme per la traccia. È possibile utilizzare il `<clear>` elemento prima di utilizzare il `<add>` elemento per essere certi che non sono presenti altri listener attivi nella raccolta.  
  
 È possibile cancellare il `Listeners` insieme a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> metodo il <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> proprietà (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.  
  
> [!NOTE]
>  Il `<clear>` elemento rimuove il <xref:System.Diagnostics.DefaultTraceListener> dal `Listeners` insieme, modifica del comportamento del <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> metodi. La chiamata a un `Assert` o `Fail` metodo in genere comporta la visualizzazione di una finestra di messaggio. Tuttavia, la finestra di messaggio non viene visualizzata se il <xref:System.Diagnostics.DefaultTraceListener> non si trova nel `Listeners` insieme.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<clear>` elemento prima di utilizzare il `<add>` elemento per aggiungere il listener `console` per il `Listeners` insieme per la traccia.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [Listener di traccia](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
