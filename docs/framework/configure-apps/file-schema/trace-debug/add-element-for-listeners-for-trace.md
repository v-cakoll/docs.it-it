---
title: <add>Elemento <listeners> per<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153672"
---
# <a name="add-element-for-listeners-for-trace"></a>\<aggiungere>elemento \<per i \<listener> per i> di tracciaAdd a Element for listeners> for trace>
Aggiunge un listener alla raccolta **Listeners.**  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>traccia**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di ascoltatori**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**type**|Attributo obbligatorio.<br /><br /> Specifica il tipo di listener. È necessario utilizzare una stringa che soddisfi i requisiti specificati in Specifica di nomi di [tipo completi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**Initializedata**|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
|**name**|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di filtro](filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a `Listeners` un listener nella raccolta per una traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener che raccoglie, archivia e instrada i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="remarks"></a>Osservazioni  
 Le <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> classi e condividono la stessa raccolta **Listeners.** Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener. Le classi listener <xref:System.Diagnostics.TraceListener>derivano da .  
  
 Se non si `name` specifica l'attributo <xref:System.Diagnostics.TraceListener.Name%2A> del listener di traccia, il valore predefinito del listener di traccia è una stringa vuota (""). Se l'applicazione dispone di un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome. Tuttavia, se l'applicazione dispone di più listener, è necessario specificare nomi univoci per ogni <xref:System.Diagnostics.Debug.Listeners%2A> listener <xref:System.Diagnostics.Trace.Listeners%2A> di traccia, che consente di identificare e gestire i singoli listener di traccia all'interno delle raccolte e .  
  
> [!NOTE]
> L'aggiunta di più listener di traccia dello stesso tipo e con lo stesso nome `Listeners` comporta l'aggiunta di un solo listener di traccia di tale tipo e nome alla raccolta. Tuttavia, è possibile aggiungere a livello `Listeners` di codice più listener identici alla raccolta.  
  
 Il valore per l'attributo **initializeData** dipende dal tipo di listener creato. Non tutti i listener di traccia richiedono l'impostazione di **initializeData**.  
  
> [!NOTE]
> Quando si `initializeData` utilizza l'attributo, è possibile che venga visualizzato l'avviso del compilatore "L'attributo 'initializeData' non è dichiarato". Questo avviso viene generato perché le impostazioni di <xref:System.Diagnostics.TraceListener>configurazione vengono convalidate rispetto alla classe base astratta , che non riconosce l'attributo `initializeData` . In genere, è possibile ignorare questo avviso per le implementazioni del listener di traccia che dispongono di un costruttore che accetta un parametro.  
  
 Nella tabella seguente vengono illustrati i listener di traccia inclusi in .NET Framework e viene descritto il valore dei relativi attributi **initializeData.**  
  
|Classe listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Valore `useErrorStream` per <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> il costruttore.  Impostare `initializeData` l'attributo su "`true`" <xref:System.Console.Error%2A?displayProperty=nameWithType>per scrivere la traccia e l'output di debug in ; "`false`" per <xref:System.Console.Out%2A?displayProperty=nameWithType>scrivere a .|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Nome del file in cui scrive <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Nome del nome di un'origine del log eventi esistente.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Nome del file in <xref:System.Diagnostics.EventSchemaTraceListener> cui viene scritto il file.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Nome del file in <xref:System.Diagnostics.TextWriterTraceListener> cui viene scritto il file.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Nome del file in <xref:System.Diagnostics.XmlWriterTraceListener> cui viene scritto il file.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ** \<** illustrato come utilizzare add `MyListener` `MyEventListener`>elementi per aggiungere i listener e per il **Listeners** insieme. `MyListener`crea un `MyListener.log` file chiamato e scrive l'output nel file. `MyEventListener`crea una voce nel registro eventi.  
  
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
