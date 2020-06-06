---
title: Elemento <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153373"
---
# <a name="listeners-element-for-trace"></a>Elemento \<listeners> per \<trace>
Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `Listeners`.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Cancella la raccolta `Listeners` per una traccia.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Rimuove un listener dalla `Listeners` raccolta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="remarks"></a>Commenti  
 Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners** . Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener. Le classi del listener fornite con la .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' **\<listeners>** elemento per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** . `MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file. `MyEventListener`Crea una voce nel log eventi.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.TraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
