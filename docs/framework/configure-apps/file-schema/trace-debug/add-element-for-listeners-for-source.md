---
title: <add>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 96bfde3ec425f6f77d1d655808d155eb0e6fcd0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927205"
---
# <a name="add-element-for-listeners-for-source"></a>\<aggiungere > elemento per \<i listener > per \<l'origine >
Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.  
  
 \<configuration>  
\<system.diagnostics>  
\<origini >  
\<> di origine  
\<listener >  
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
|`type`|Attributo obbligatorio, a meno che non si faccia riferimento a un `sharedListeners` listener nella raccolta. in tal caso, è necessario fare riferimento solo al nome (vedere l' [esempio](#example)).<br /><br /> Specifica il tipo di listener. È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata. Viene <xref:System.Configuration.ConfigurationException> generata un'eccezione se la classe non dispone di un costruttore che accetta una stringa.|  
|`name`|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
|`traceOutputOptions`|Attributo facoltativo.<br /><br /> Specifica il <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valore della proprietà per il listener di traccia.|  
|[attributi personalizzati]|Attributi facoltativi.<br /><br /> Specifica il valore per gli attributi specifici del listener identificati <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> dal metodo per il listener. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>è un esempio di attributo aggiuntivo univoco per la <xref:System.Diagnostics.DelimitedListTraceListener> classe.|  
  
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
 Le classi del listener fornite con la .NET Framework derivano <xref:System.Diagnostics.TraceListener> dalla classe.  
  
 Se non si specifica l' `name` attributo del listener di traccia, per impostazione predefinita la <xref:System.Diagnostics.TraceListener.Name%2A> proprietà del listener di traccia è una stringa vuota (""). Se l'applicazione dispone di un solo listener, è possibile aggiungerla senza specificare un nome ed è possibile rimuoverla specificando una stringa vuota per il nome. Tuttavia, se l'applicazione ha più di un listener, è necessario specificare un nome univoco per ogni listener di traccia, che consente di identificare e gestire i <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> singoli listener di traccia nella raccolta.  
  
> [!NOTE]
> L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia del tipo e del nome alla `Listeners` raccolta. Tuttavia, è possibile aggiungere a livello di codice più listener identici `Listeners` alla raccolta.  
  
 Il valore `initializeData` dell'attributo dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono che venga `initializeData`specificato.  
  
> [!NOTE]
> Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla <xref:System.Diagnostics.TraceListener>classe di base astratta, che `initializeData` non riconosce l'attributo. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore dei rispettivi `initializeData` attributi.  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>costruttore. `useErrorStream`  Impostare l' `initializeData` attributo su "`true`" per scrivere l'output di traccia e di debug nel flusso di errore standard. impostarlo su "`false`" per scrivere nel flusso di output standard.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nome del file <xref:System.Diagnostics.DelimitedListTraceListener> in cui scrive.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in cui <xref:System.Diagnostics.EventSchemaTraceListener> scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui <xref:System.Diagnostics.TextWriterTraceListener> scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui <xref:System.Diagnostics.XmlWriterTraceListener> scrive.|  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare `<add>` gli elementi per aggiungere i `console` listener e `textListener` alla `Listeners` raccolta per l'origine `TraceSourceApp`di traccia. Il `textListener` listener scrive l'output di traccia nel file listener. log.  
  
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
