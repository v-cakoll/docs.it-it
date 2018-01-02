---
title: '&lt;aggiungere&gt; elemento per &lt;sharedListeners&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 490e58d4514667c5ec781dd76644012b0c97509d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;aggiungere&gt; elemento per &lt;sharedListeners&gt;
Aggiunge un listener alla raccolta `sharedListeners`. `sharedListeners`è una raccolta di listener che qualsiasi [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) possono fare riferimento.  Per impostazione predefinita, nei listener di `sharedListeners` insieme non vengono inseriti in un `Listeners` insieme. Devono essere aggiunti in base al nome per il [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). Non è possibile ottenere i listener `sharedListeners` insieme nel codice in fase di esecuzione.  
  
 \<configuration>  
\<System. Diagnostics >  
\<sharedListeners > elemento  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome del listener che consente di aggiungere il listener condiviso a un `Listeners` insieme.|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo del listener. È necessario utilizzare una stringa che soddisfi i requisiti indicati in [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> La stringa passata al costruttore per la classe specificata.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Aggiunge un filtro a un listener nella raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sharedListeners`|Una raccolta di listener che qualsiasi origine o un elemento di traccia può fare riferimento.|  
  
## <a name="remarks"></a>Note  
 Le classi di listener fornite con .NET Framework derivano dalla <xref:System.Diagnostics.TraceListener> classe. Il valore per il `name` attributo viene utilizzato per aggiungere il listener condiviso a un `Listeners` insieme per una traccia o da un'origine di traccia. Il valore per il `initializeData` attributo dipende dal tipo di listener creato. Non tutti i listener di traccia è necessario specificare `initializeData`.  
  
> [!NOTE]
>  Quando si utilizza il `initializeData` attributo, è possibile che venga visualizzato l'avviso "l'attributo 'initializeData' non dichiarato." del compilatore Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo. In genere, è possibile ignorare questo avviso per le implementazioni di listener di traccia che dispone di un costruttore che accetta un parametro.  
  
 Nella tabella seguente mostra i listener di traccia inclusi in .NET Framework e descrive il valore della loro `initializeData` attributi.  
  
|Classe di listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.  Impostare il `initializeData` attributo "`true`"per scrivere output di traccia e debug nel flusso di errore standard; impostarla su"`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Il nome di un'origine di log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare `<add>` elementi da aggiungere il <xref:System.Diagnostics.TextWriterTraceListener> `textListener` per il `sharedListeners` insieme.   `textListener`viene aggiunto per nome per il `Listeners` raccolta per l'origine di traccia `TraceSourceApp`. Il `textListener` listener scrive output di traccia nel file myListener.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Listener di traccia](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
