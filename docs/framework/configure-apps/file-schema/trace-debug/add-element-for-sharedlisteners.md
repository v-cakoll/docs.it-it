---
title: Elemento <add> per <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927219"
---
# <a name="add-element-for-sharedlisteners"></a>\<aggiungere > elemento per \<sharedListeners >
Aggiunge un listener alla raccolta `sharedListeners`. `sharedListeners`è una raccolta di listener a cui può fare riferimento qualsiasi [ \<> di origine](source-element.md) o [ \<> di traccia](trace-element.md) .  Per impostazione predefinita, i `sharedListeners` listener nella raccolta non vengono inseriti in una `Listeners` raccolta. Devono essere aggiunti per nome al > di [ \<origine](source-element.md) o [ \<> di traccia](trace-element.md). Non è possibile ottenere i listener nella `sharedListeners` raccolta nel codice in fase di esecuzione.  
  
 \<configuration>  
&nbsp;&nbsp;\<system.diagnostics>  
&nbsp;&nbsp;&nbsp;&nbsp;\<Elemento > sharedListeners  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome del listener utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta.|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo di listener. È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
|`traceOutputOptions`|Attributo facoltativo.<br/><br/>Rappresentazione di stringa di uno o più <xref:System.Diagnostics.TraceOptions> membri dell'enumerazione che indica i dati da scrivere nell'output di traccia. Più elementi sono separati da virgole. Il valore predefinito è "None".|

### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Aggiunge un filtro a un listener nella raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sharedListeners`|Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.|  
  
## <a name="remarks"></a>Note  
 Le classi del listener fornite con la .NET Framework derivano <xref:System.Diagnostics.TraceListener> dalla classe. Il valore per l' `name` attributo viene utilizzato per aggiungere il listener condiviso a una `Listeners` raccolta per una traccia o un'origine di traccia. Il valore `initializeData` dell'attributo dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono che venga `initializeData`specificato.  
  
> [!NOTE]
> Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla <xref:System.Diagnostics.TraceListener>classe di base astratta, che `initializeData` non riconosce l'attributo. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore dei rispettivi `initializeData` attributi.  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>costruttore. `useErrorStream`  Impostare l' `initializeData` attributo su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarlo su "`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nome del file <xref:System.Diagnostics.DelimitedListTraceListener> in cui scrive.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in cui <xref:System.Diagnostics.EventSchemaTraceListener> scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui <xref:System.Diagnostics.TextWriterTraceListener> scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nome del file in cui <xref:System.Diagnostics.XmlWriterTraceListener> scrive.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare `<add>` gli elementi per aggiungere <xref:System.Diagnostics.TextWriterTraceListener> l'oggetto `sharedListeners` `textListener` alla raccolta.   `textListener`viene aggiunto per nome alla `Listeners` raccolta per l'origine `TraceSourceApp`di traccia. Il `textListener` listener scrive l'output di traccia nel file listener. log.  
  
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

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
