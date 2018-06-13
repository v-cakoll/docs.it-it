---
title: '&lt;filtro&gt; elemento per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;traccia&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 095212f73adb906d9d80db747c331c436c1cf846
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745786"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a>&lt;filtro&gt; elemento per &lt;aggiungere&gt; per &lt;listener&gt; per &lt;traccia&gt;
Aggiunge un filtro a un listener di `Listeners` insieme per una traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
\<traccia >  
\<listener >  
\<add>  
\<Filtro >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo di filtro, che deve ereditare la <xref:System.Diagnostics.TraceFilter> classe. È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde al tipo <xref:System.Type.FullName%2A> proprietà, oppure è possibile utilizzare il nome completo del tipo tra cui le informazioni sull'assembly, che corrisponde alla <xref:System.Type.AssemblyQualifiedName%2A> proprietà. Per informazioni sui nomi di tipo completo, vedere [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> La stringa passata al costruttore per la classe di filtro specificato.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener di raccolgano, archiviano e indirizzare i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`add`|Aggiunge un listener alla raccolta `Listeners`.|  
  
## <a name="remarks"></a>Note  
 Il `<filter>` elemento deve essere contenuto in un `<add>` elemento per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md). Se il listener è definito in un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.  
  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<filter>` elemento per aggiungere un filtro al listener `console` nel `Listeners` insieme per la traccia, che specifica il livello di evento di filtro come `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
