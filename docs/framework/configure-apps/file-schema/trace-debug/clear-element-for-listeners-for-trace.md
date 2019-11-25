---
title: Elemento <clear> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088921"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<elemento clear > per \<listeners > per \<Trace >
Cancella la raccolta `Listeners` per una traccia.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**Trace**](trace-element.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**listener**](listeners-element-for-trace.md)\<
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**deselezionare >**

## <a name="syntax"></a>Sintassi  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<clear>` rimuove tutti i listener dalla raccolta `Listeners` per Trace. È possibile utilizzare l'elemento `<clear>` prima di utilizzare l'elemento `<add>` per verificare che non siano presenti altri listener attivi nella raccolta.  
  
 È possibile cancellare il `Listeners` raccolta a livello di codice chiamando il metodo <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> sulla proprietà <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
> [!NOTE]
> L'elemento `<clear>` rimuove la <xref:System.Diagnostics.DefaultTraceListener> dalla raccolta `Listeners`, modificando il comportamento dei metodi <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. La chiamata di un metodo di `Assert` o `Fail` comporta in genere la visualizzazione di una finestra di messaggio. Tuttavia, la finestra di messaggio non viene visualizzata se la <xref:System.Diagnostics.DefaultTraceListener> non è presente nella raccolta `Listeners`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento `<clear>` prima di utilizzare l'elemento `<add>` per aggiungere il listener `console` alla raccolta `Listeners` per Trace.  
  
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
