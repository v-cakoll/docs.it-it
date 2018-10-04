---
title: '&lt;aggiungere&gt; (elemento) per &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 93fdb548882422634e1d2456b4d37f434b278f8d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777828"
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;aggiungere&gt; (elemento) per &lt;sharedListeners&gt;
Aggiunge un listener alla raccolta `sharedListeners`. `sharedListeners` è una raccolta di listener che eventuali [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oppure [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) può fare riferimento.  Per impostazione predefinita, nei listener di traccia le `sharedListeners` raccolta non vengono inserite in un `Listeners` raccolta. Devono essere aggiunti in base al nome per il [ \<origine >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) oppure [ \<traccia >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). Non è possibile ottenere il listener `sharedListeners` insieme nel codice in fase di esecuzione.  
  
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
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome del listener che consente di aggiungere il listener condiviso a un `Listeners` raccolta.|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo del listener. È necessario usare una stringa che soddisfi i requisiti specificati nelle [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
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
|`sharedListeners`|Raccolta di listener che possono fare riferimento qualsiasi origine o un elemento di traccia.|  
  
## <a name="remarks"></a>Note  
 Le classi di listener fornite con .NET Framework derivano dal <xref:System.Diagnostics.TraceListener> classe. Il valore per il `name` attributo è usato per aggiungere il listener condiviso per un `Listeners` insieme per un'analisi o un'origine di traccia. Il valore per il `initializeData` attributo dipende dal tipo di listener creato. Non tutti i listener di traccia è necessario specificare `initializeData`.  
  
> [!NOTE]
>  Quando si usa il `initializeData` attributo, è possibile che venga visualizzato l'avviso "non è dichiarato l'attributo 'attributo initializeData'." del compilatore Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispone di un costruttore che accetta un parametro.  
  
 Nella tabella seguente mostra i listener di traccia incluse in .NET Framework e descrive il valore della loro `initializeData` attributi.  
  
|Classe di listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.  Impostare il `initializeData` dell'attributo "`true`"per scrivere output di traccia e debug nel flusso di errore standard; impostarlo su"`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Il nome di un'origine di log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare `<add>` elementi da aggiungere i <xref:System.Diagnostics.TextWriterTraceListener> `textListener` per il `sharedListeners` raccolta.   `textListener` viene aggiunto in base al nome per il `Listeners` insieme per l'origine di traccia `TraceSourceApp`. Il `textListener` listener scrive output di traccia nel file myListener.  
  
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
