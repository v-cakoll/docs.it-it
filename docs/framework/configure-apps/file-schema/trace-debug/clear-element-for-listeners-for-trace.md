---
title: <clear>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927176"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<Cancella > elemento per \<i listener > per \<la traccia >
Cancella la raccolta `Listeners` per una traccia.  
  
 \<configuration>  
\<system.diagnostics>  
\<traccia >  
\<listener >  
\<Cancella >  
  
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
|`listeners`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
  
## <a name="remarks"></a>Note  
 L' `<clear>` elemento rimuove tutti i listener `Listeners` dalla raccolta per Trace. È possibile usare l' `<clear>` elemento prima di usare `<add>` l'elemento per assicurarsi che non ci siano altri listener attivi nella raccolta.  
  
 È possibile cancellare la `Listeners` raccolta a livello di codice chiamando <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> il metodo sulla <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> proprietà (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
> [!NOTE]
> L' `<clear>` elemento <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> rimuove dalla raccolta,<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>modificando il comportamento dei metodi ,,e.<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> `Listeners` <xref:System.Diagnostics.DefaultTraceListener> La chiamata `Assert` di `Fail` un metodo o determina in genere la visualizzazione di una finestra di messaggio. Tuttavia, la finestra <xref:System.Diagnostics.DefaultTraceListener> `Listeners` di messaggio non viene visualizzata se l'oggetto non è presente nella raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `<clear>` elemento prima di utilizzare `<add>` l'elemento per `Listeners` aggiungere il `console` listener alla raccolta per Trace.  
  
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

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Schema delle impostazioni di traccia e debug](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
