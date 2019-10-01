---
title: Elemento <remove> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697224"
---
# <a name="remove-element-for-listeners-for-trace"></a>Elemento > \<remove per \<listeners > per \<trace >
Rimuove un listener dalla raccolta **Listeners** .  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**name**|Attributo obbligatorio.<br /><br /> Nome del listener da rimuovere dalla raccolta **Listeners** .|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Configura il servizio di traccia ASP.NET.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> La rimozione di <xref:System.Diagnostics.DefaultTraceListener> dalla raccolta `Listeners` modifica il comportamento dei metodi <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> e <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. La chiamata di un metodo `Assert` o `Fail` comporta in genere la visualizzazione di una finestra di messaggio, ma la finestra di messaggio non viene visualizzata se la <xref:System.Diagnostics.DefaultTraceListener> non è presente nella raccolta `Listeners`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come rimuovere il listener di traccia predefinito dalla raccolta di **listener** di traccia.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
