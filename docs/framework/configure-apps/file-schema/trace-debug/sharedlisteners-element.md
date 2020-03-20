---
title: <sharedListeners> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153321"
---
# <a name="sharedlisteners-element"></a>\<Elemento> sharedListeners
Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.  Questi listener non ricevono alcuna traccia per impostazione predefinita e non è possibile recuperarli in fase di esecuzione. I listener identificati come listener condivisi possono essere aggiunti alle origini o alle tracce in base al nome.  
  
[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<>sharedListeners**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<aggiungere>](add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`Configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Osservazioni  
 L'aggiunta di un listener alla raccolta di listener condivisi non lo rende un listener attivo. Deve comunque essere aggiunto a un'origine di `Listeners` traccia o a una traccia aggiungendola alla raccolta per tale elemento di traccia. Le classi listener in .NET <xref:System.Diagnostics.TraceListener> Framework derivano dalla classe .  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene `<sharedListeners>` illustrato come utilizzare `console` l'elemento per aggiungere il listener alla `Listeners` raccolta per le classi <xref:System.Diagnostics.TraceSource> e <xref:System.Diagnostics.Trace> . Il listener di traccia della console scrive <xref:System.Diagnostics.TraceSource> le <xref:System.Diagnostics.Trace>informazioni di traccia nella console tramite chiamate a o .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
