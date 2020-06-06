---
title: <add>Elemento per <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153672"
---
# <a name="add-element-for-listeners-for-trace"></a>\<add>Elemento per \<listeners> per\<trace>
Aggiunge un listener alla raccolta **Listeners** .  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**type**|Attributo obbligatorio.<br /><br /> Specifica il tipo di listener. È necessario usare una stringa che soddisfi i requisiti specificati per [specificare nomi di tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
|**nome**|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a un listener nella `Listeners` raccolta per una traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="remarks"></a>Commenti  
 Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners** . Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener. Le classi del listener derivano da <xref:System.Diagnostics.TraceListener> .  
  
 Se non si specifica l' `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> valore predefinito di per il listener di traccia è una stringa vuota (""). Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome. Tuttavia, se l'applicazione ha più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle <xref:System.Diagnostics.Debug.Listeners%2A> <xref:System.Diagnostics.Trace.Listeners%2A> raccolte e.  
  
> [!NOTE]
> L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia del tipo e del nome alla `Listeners` raccolta. Tuttavia, è possibile aggiungere a livello di codice più listener identici alla `Listeners` raccolta.  
  
 Il valore dell'attributo **initializeData** dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono che venga specificato **initializeData**.  
  
> [!NOTE]
> Quando si usa l' `initializeData` attributo, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener> , che non riconosce l' `initializeData` attributo. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi **initializeData** .  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream`Valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.  Impostare l' `initializeData` attributo su " `true` " per scrivere l'output di traccia ed eseguire il debug in <xref:System.Console.Error%2A?displayProperty=nameWithType> ; " `false` " in cui scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType> .|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome del nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file <xref:System.Diagnostics.EventSchemaTraceListener> in cui scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file <xref:System.Diagnostics.TextWriterTraceListener> in cui scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nome del file <xref:System.Diagnostics.XmlWriterTraceListener> in cui scrive.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare **\<add>** gli elementi per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** . `MyListener`Crea un file denominato `MyListener.log` e scrive l'output nel file. `MyEventListener`Crea una voce nel log eventi.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
