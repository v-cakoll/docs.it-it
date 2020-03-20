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
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153607"
---
# <a name="add-element-for-sharedlisteners"></a>\<Aggiungere elemento \<> per la> sharedListenersAdd a Element for sharedListeners>
Aggiunge un listener alla raccolta `sharedListeners`. `sharedListeners`è una raccolta di [ \<](source-element.md) listener a cui possono fare riferimento qualsiasi>di origine o [ \<>](trace-element.md) di traccia.  Per impostazione predefinita, `sharedListeners` i listener nella `Listeners` raccolta non vengono inseriti in una raccolta. Devono essere aggiunti in [ \<](source-element.md) base al nome al>di origine o [ \< ](trace-element.md)>di traccia . Non è possibile ottenere i listener `sharedListeners` nella raccolta nel codice in fase di esecuzione.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>sharedListeners**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**

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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Specifica il nome del listener utilizzato per aggiungere il `Listeners` listener condiviso a una raccolta.|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo di listener. È necessario utilizzare una stringa che soddisfi i requisiti specificati in Specifica di nomi di [tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
|`traceOutputOptions`|Attributo facoltativo.<br/><br/>Rappresentazione di stringa <xref:System.Diagnostics.TraceOptions> di uno o più membri di enumerazione che indicano i dati da scrivere nell'output di traccia. Più elementi sono separati da virgole. Il valore predefinito è "None".|

### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di filtro](filter-element-for-add-for-sharedlisteners.md)|Aggiunge un filtro a un listener nella raccolta `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sharedListeners`|Raccolta di listener a cui può fare riferimento qualsiasi elemento di origine o di traccia.|  
  
## <a name="remarks"></a>Osservazioni  
 Le classi listener fornite con .NET <xref:System.Diagnostics.TraceListener> Framework derivano dalla classe . Il valore `name` dell'attributo viene utilizzato per `Listeners` aggiungere il listener condiviso a una raccolta per una traccia o un'origine di traccia. Il valore `initializeData` dell'attributo dipende dal tipo di listener creato. Non tutti i listener di `initializeData`traccia richiedono l'impostazione di .  
  
> [!NOTE]
> Quando si `initializeData` utilizza l'attributo, è possibile che venga visualizzato l'avviso del compilatore "L'attributo 'initializeData' non è dichiarato". Questo avviso viene generato perché le impostazioni di <xref:System.Diagnostics.TraceListener>configurazione vengono convalidate rispetto alla classe base astratta , che non riconosce l'attributo `initializeData` . In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi in .NET Framework e viene descritto il valore dei relativi `initializeData` attributi.  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|Valore `useErrorStream` per <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> il costruttore.  Impostare `initializeData` l'attributo su "`true`" per scrivere la traccia e l'output di debug nel flusso di errore standard; impostarlo su`false`" " per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in <xref:System.Diagnostics.EventSchemaTraceListener> cui viene scritto il file.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in <xref:System.Diagnostics.TextWriterTraceListener> cui viene scritto il file.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Nome del file in <xref:System.Diagnostics.XmlWriterTraceListener> cui viene scritto il file.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene `<add>` illustrato come <xref:System.Diagnostics.TextWriterTraceListener> `textListener` utilizzare `sharedListeners` gli elementi per aggiungere l'oggetto alla raccolta.   `textListener`viene aggiunto in `Listeners` base al nome `TraceSourceApp`all'insieme per l'origine di traccia. Il `textListener` listener scrive l'output di traccia nel file myListener.log.  
  
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
