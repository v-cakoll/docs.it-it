---
title: Elemento <add> per <listeners> per <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 0818d7ec248b210f215759069b9f69a3e29637f5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699399"
---
# <a name="add-element-for-listeners-for-source"></a>Elemento > \<add per \<listeners > per \<source >
Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**  
  
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
|`type`|Attributo obbligatorio, a meno che non si faccia riferimento a un listener nella raccolta `sharedListeners`, nel qual caso è necessario fare riferimento solo al nome (vedere l' [esempio](#example)).<br /><br /> Specifica il tipo di listener. È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata. Viene generato un <xref:System.Configuration.ConfigurationException> se la classe non dispone di un costruttore che accetta una stringa.|  
|`name`|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
|`traceOutputOptions`|Attributo facoltativo.<br /><br /> Specifica il valore della proprietà <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> per il listener di traccia.|  
|[attributi personalizzati]|Attributi facoltativi.<br /><br /> Specifica il valore per gli attributi specifici del listener identificati dal metodo <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> per il listener. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> è un esempio di attributo aggiuntivo univoco per la classe <xref:System.Diagnostics.DelimitedListTraceListener>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sources`|Contiene le origini di traccia che avviano i messaggi di traccia.|  
|`source`|Specifica un'origine di traccia che avvia i messaggi di traccia.|  
|`listeners`|Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.|  
  
## <a name="remarks"></a>Note  
 Le classi del listener fornite con la .NET Framework derivano dalla classe <xref:System.Diagnostics.TraceListener>.  
  
 Se non si specifica l'attributo `name` del listener di traccia, il valore predefinito della proprietà <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia è una stringa vuota (""). Se l'applicazione dispone di un solo listener, è possibile aggiungerla senza specificare un nome ed è possibile rimuoverla specificando una stringa vuota per il nome. Tuttavia, se l'applicazione ha più di un listener, è necessario specificare un nome univoco per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia nella raccolta <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> L'aggiunta di più di un listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia di quel tipo e del nome alla raccolta `Listeners`. Tuttavia, è possibile aggiungere a livello di codice più listener identici alla raccolta `Listeners`.  
  
 Il valore dell'attributo `initializeData` dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono di specificare `initializeData`.  
  
> [!NOTE]
> Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi `initializeData`.  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Valore `useErrorStream` per il costruttore <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarla su "`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare gli elementi `<add>` per aggiungere i listener `console` e `textListener` alla raccolta `Listeners` per l'origine di traccia `TraceSourceApp`. Il listener `textListener` scrive l'output di traccia nel file listener. log.  
  
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
