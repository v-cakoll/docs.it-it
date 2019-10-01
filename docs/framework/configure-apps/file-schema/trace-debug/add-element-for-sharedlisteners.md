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
ms.openlocfilehash: 0c7665898f8c625c2d07b67ea6c7fe25113fddd8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699481"
---
# <a name="add-element-for-sharedlisteners"></a>Elemento > \<add per \<sharedListeners >
Aggiunge un listener alla raccolta `sharedListeners`. `sharedListeners` è una raccolta di listener a cui può fare riferimento qualsiasi [\<source >](source-element.md) o [\<trace >](trace-element.md) .  Per impostazione predefinita, i listener nella raccolta `sharedListeners` non vengono inseriti in una raccolta `Listeners`. Devono essere aggiunti per nome al [> \<SOURCE](source-element.md) o [\<trace >](trace-element.md). Non è possibile ottenere i listener nella raccolta `sharedListeners` nel codice in fase di esecuzione.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sharedListeners >** ](sharedlisteners-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**  
  
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
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome del listener utilizzato per aggiungere il listener condiviso a una raccolta `Listeners`.|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo di listener. È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
|`traceOutputOptions`|Attributo facoltativo.<br/><br/>Rappresentazione di stringa di uno o più membri dell'enumerazione <xref:System.Diagnostics.TraceOptions> che indica i dati da scrivere nell'output di traccia. Più elementi sono separati da virgole. Il valore predefinito è "None".|

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
 Le classi del listener fornite con la .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>. Il valore per l'attributo `name` viene utilizzato per aggiungere il listener condiviso a una raccolta `Listeners` per una traccia o un'origine di traccia. Il valore dell'attributo `initializeData` dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono di specificare `initializeData`.  
  
> [!NOTE]
> Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi `initializeData`.  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Valore `useErrorStream` per il costruttore <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarla su "`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nome del file in cui viene scritto <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare gli elementi `<add>` per aggiungere la <xref:System.Diagnostics.TextWriterTraceListener> @ no__t-2 alla raccolta `sharedListeners`.   `textListener` viene aggiunto per nome alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`. Il listener `textListener` scrive l'output di traccia nel file listener. log.  
  
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
