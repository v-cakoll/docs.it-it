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
ms.openlocfilehash: 48cb59dfc0871822bfcff5e16d4283008a411479
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701216"
---
# <a name="sharedlisteners-element"></a>\<sharedListeners > elemento
Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.  Questi listener non ricevono tutte le tracce per impostazione predefinita e non è possibile recuperare questi listener in fase di esecuzione. I listener identificati come listener condivisi possono essere aggiunti alle origini o delle tracce in base al nome.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Aggiunge un listener alla raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`Configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Note  
 Aggiunta di un listener per la raccolta di listener condivisi non renderlo un listener attivo. È necessario comunque aggiungerlo a un'origine di traccia o da una traccia, aggiungerlo al `Listeners` raccolta per tale elemento di traccia. Le classi di listener in .NET Framework derivano dal <xref:System.Diagnostics.TraceListener> classe.  
  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<sharedListeners>` elemento a cui aggiungere il listener `console` per il `Listeners` raccolta sia per il <xref:System.Diagnostics.TraceSource> e <xref:System.Diagnostics.Trace> classi. Il listener di traccia console scrive le informazioni di traccia nella console mediante chiamate a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.  
  
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
- [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Listener di traccia](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
