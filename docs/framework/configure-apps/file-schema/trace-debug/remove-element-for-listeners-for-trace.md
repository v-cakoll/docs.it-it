---
title: <remove>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 0c5c9efb8a22d26ea5d4467f9628af5935d6dbad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920481"
---
# <a name="remove-element-for-listeners-for-trace"></a>\<rimuovere > elemento per \<i listener > per \<la traccia >
Rimuove un listener dalla raccolta **Listeners** .  
  
 \<configuration>  
\<system.diagnostics>  
\<traccia >  
\<listener >  
\<remove>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**name**|Attributo obbligatorio.<br /><br /> Nome del listener da rimuovere dalla raccolta Listeners .|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Configura il servizio di traccia ASP.NET.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Larimozionedidalla<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>raccoltamodificail comportamento dei metodi,, e. `Listeners` <xref:System.Diagnostics.DefaultTraceListener> La chiamata `Assert` di `Fail` un metodo o determina in genere la visualizzazione di una finestra di messaggio, ma la finestra di messaggio non <xref:System.Diagnostics.DefaultTraceListener> viene visualizzata se `Listeners` l'oggetto non è presente nella raccolta.  
  
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
