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
ms.openlocfilehash: b419ecf451b79808e545525c7b8761175f390200
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699296"
---
# <a name="sharedlisteners-element"></a>Elemento > \<sharedListeners
Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.  Questi listener non ricevono alcuna traccia per impostazione predefinita e non è possibile recuperare questi listener in fase di esecuzione. I listener identificati come listener condivisi possono essere aggiunti alle origini o alle tracce in base al nome.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<sharedListeners >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`Configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Note  
 L'aggiunta di un listener alla raccolta di listener condivisi non lo rende un listener attivo. È comunque necessario aggiungerlo a un'origine di traccia o a una traccia aggiungendolo alla raccolta `Listeners` per l'elemento Trace. Le classi listener nel .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>.  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento `<sharedListeners>` per aggiungere il listener `console` alla raccolta `Listeners` per le classi <xref:System.Diagnostics.TraceSource> e <xref:System.Diagnostics.Trace>. Il listener di traccia della console scrive le informazioni di traccia nella console tramite chiamate a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.  
  
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
