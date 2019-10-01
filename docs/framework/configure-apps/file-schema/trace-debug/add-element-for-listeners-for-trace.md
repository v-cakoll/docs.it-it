---
title: Elemento <add> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d89a77107e7aff65b007a69c23af34771146570c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697332"
---
# <a name="add-element-for-listeners-for-trace"></a>Elemento > \<add per \<listeners > per \<trace >
Aggiunge un listener alla raccolta **Listeners** .  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**  
  
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
|**name**|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a un listener nella raccolta `Listeners` per una traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="remarks"></a>Note  
 Le classi <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono la stessa raccolta **Listeners** . Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizzerà lo stesso listener. Le classi listener derivano da <xref:System.Diagnostics.TraceListener>.  
  
 Se non si specifica l'attributo `name` del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia viene impostato come valore predefinito su una stringa vuota (""). Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome. Tuttavia, se l'applicazione ha più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle raccolte <xref:System.Diagnostics.Debug.Listeners%2A> e <xref:System.Diagnostics.Trace.Listeners%2A>.  
  
> [!NOTE]
> L'aggiunta di più di un listener di traccia dello stesso tipo e con lo stesso nome comporta l'aggiunta di un solo listener di traccia di quel tipo e del nome alla raccolta `Listeners`. Tuttavia, è possibile aggiungere a livello di codice più listener identici alla raccolta `Listeners`.  
  
 Il valore dell'attributo **initializeData** dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono che venga specificato **initializeData**.  
  
> [!NOTE]
> Quando si usa l'attributo `initializeData`, è possibile che venga visualizzato l'avviso del compilatore "l'attributo ' initializeData ' non è dichiarato". Questo avviso si verifica perché le impostazioni di configurazione vengono convalidate rispetto alla classe di base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce l'attributo `initializeData`. In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi nel .NET Framework e viene descritto il valore degli attributi **initializeData** .  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Valore `useErrorStream` per il costruttore <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.  Impostare l'attributo `initializeData` su "`true`" per scrivere l'output di traccia ed eseguire il debug in <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" per scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome del nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.EventSchemaTraceListener>.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.TextWriterTraceListener>.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nome del file in cui viene scritto il <xref:System.Diagnostics.XmlWriterTraceListener>.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare gli elementi **> \<ADD** per aggiungere i listener `MyListener` e `MyEventListener` alla raccolta **Listeners** . `MyListener` crea un file denominato `MyListener.log` e scrive l'output nel file. `MyEventListener` crea una voce nel registro eventi.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Schema delle impostazioni di traccia e debug](index.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
