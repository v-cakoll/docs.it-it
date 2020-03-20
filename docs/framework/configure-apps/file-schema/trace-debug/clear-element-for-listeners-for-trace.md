---
title: <clear>Elemento <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153542"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<Clear> \<Element per \<i> di listener per i> di traccia
Cancella la raccolta `Listeners` per una traccia.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>traccia**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>chiari**

## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener che raccolgono, archiviano e instradano i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento `<clear>` rimuove tutti `Listeners` i listener dalla raccolta per la traccia. È possibile `<clear>` utilizzare l'elemento prima di utilizzare l'elemento `<add>` per essere certi che non siano presenti altri listener attivi nella raccolta.  
  
 È possibile `Listeners` cancellare l'insieme <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> a <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> livello`System.Diagnostics.Trace.Listeners.Clear()`di codice chiamando il metodo sulla proprietà ( ).  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.  
  
> [!NOTE]
> L'elemento `<clear>` <xref:System.Diagnostics.DefaultTraceListener> rimuove `Listeners` l'oggetto dall'insieme, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>alterando il comportamento dei metodi , , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . La `Assert` chiamata `Fail` a un metodo o comporta in genere la visualizzazione di una finestra di messaggio. Tuttavia, la finestra di messaggio <xref:System.Diagnostics.DefaultTraceListener> non viene `Listeners` visualizzata se l'oggetto non è presente nella raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene `<clear>` illustrato come `<add>` utilizzare l'elemento `console` prima `Listeners` di utilizzare l'elemento per aggiungere il listener alla raccolta per la traccia.  
  
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
- [\<rimuovere>](remove-element-for-listeners-for-trace.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
