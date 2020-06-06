---
title: <clear>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153542"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<clear>Elemento per \<listeners> per\<trace>
Cancella la raccolta `Listeners` per una traccia.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
  
## <a name="remarks"></a>Commenti  
 L' `<clear>` elemento rimuove tutti i listener dalla `Listeners` raccolta per Trace. È possibile usare l' `<clear>` elemento prima di usare l' `<add>` elemento per assicurarsi che non ci siano altri listener attivi nella raccolta.  
  
 È possibile cancellare la `Listeners` raccolta a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> Metodo sulla <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Proprietà ( `System.Diagnostics.Trace.Listeners.Clear()` ).  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
> [!NOTE]
> L' `<clear>` elemento rimuove <xref:System.Diagnostics.DefaultTraceListener> dalla `Listeners` raccolta, modificando il comportamento dei <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metodi,, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . La chiamata `Assert` `Fail` di un metodo o determina in genere la visualizzazione di una finestra di messaggio. Tuttavia, la finestra di messaggio non viene visualizzata se l'oggetto <xref:System.Diagnostics.DefaultTraceListener> non è presente nella `Listeners` raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `<clear>` elemento prima di utilizzare l' `<add>` elemento per aggiungere il listener `console` alla `Listeners` raccolta per Trace.  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Schema delle impostazioni di traccia e debug](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
