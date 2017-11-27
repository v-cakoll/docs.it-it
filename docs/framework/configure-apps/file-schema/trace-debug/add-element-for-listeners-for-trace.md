---
title: '&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: "24"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bbb74d9a542833a96c61bcc09f6e4e5f0807843d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;aggiungere&gt; elemento per &lt;listener&gt; per &lt;traccia&gt;
Aggiunge un listener per il **listener** insieme.  
  
 \<configuration>  
\<System. Diagnostics >  
\<traccia >  
\<listener >  
\<add>  
  
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
|**type**|Attributo obbligatorio.<br /><br /> Specifica il tipo del listener. È necessario utilizzare una stringa che soddisfi i requisiti indicati in [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**attributo initializeData**|Attributo facoltativo.<br /><br /> La stringa passata al costruttore per la classe specificata.|  
|**name**|Attributo facoltativo.<br /><br /> Specifica il nome del listener.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Aggiunge un filtro a un listener di `Listeners` insieme per una traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`listeners`|Specifica un listener per la raccolta, la memorizzazione e indirizza i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`system.diagnostics`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
  
## <a name="remarks"></a>Note  
 Il <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.Trace> condividono lo stesso **listener** insieme. Se si aggiunge un oggetto listener alla raccolta in una di queste classi, l'altra classe utilizza lo stesso listener. Derivano le classi di listener di <xref:System.Diagnostics.TraceListener>.  
  
 Se non si specifica il `name` attributo del listener di traccia, il <xref:System.Diagnostics.TraceListener.Name%2A> delle impostazioni predefinite del listener di traccia in una stringa vuota (""). Se l'applicazione presenta un solo listener, è possibile aggiungerlo senza specificare un nome e rimuoverlo specificando una stringa vuota per il nome. Tuttavia, se l'applicazione presenta più di un listener, è necessario specificare nomi univoci per ogni listener di traccia, che consente di identificare e gestire singoli listener di traccia all'interno di <xref:System.Diagnostics.Debug.Listeners%2A> e <xref:System.Diagnostics.Trace.Listeners%2A> raccolte.  
  
> [!NOTE]
>  Aggiunta di più di un listener di traccia, dello stesso tipo e con lo stesso nome risultati in un solo listener di traccia di quel tipo e nome viene aggiunto al `Listeners` insieme. Tuttavia, è possibile aggiungere a livello di codice più listener identici per il `Listeners` insieme.  
  
 Il valore per il **initializeData** attributo dipende dal tipo di listener creato. Non tutti i listener di traccia è necessario specificare **initializeData**.  
  
> [!NOTE]
>  Quando si utilizza il `initializeData` attributo, è possibile che venga visualizzato l'avviso "l'attributo 'initializeData' non dichiarato." del compilatore Questo avviso viene generato perché le impostazioni di configurazione vengono convalidate in base alla classe base astratta <xref:System.Diagnostics.TraceListener>, che non riconosce il `initializeData` attributo. In genere, è possibile ignorare questo avviso per le implementazioni di listener di traccia che dispone di un costruttore che accetta un parametro.  
  
 Nella tabella seguente mostra i listener di traccia inclusi in .NET Framework e descrive il valore della loro **initializeData** attributi.  
  
|Classe di listener di traccia|valore dell'attributo initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|Il `useErrorStream` valore per il <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> costruttore.  Impostare il `initializeData` attributo "`true`" per scrivere una traccia e debug di output per <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" per scrivere <xref:System.Console.Out%2A?displayProperty=nameWithType>.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Il nome del file di <xref:System.Diagnostics.DelimitedListTraceListener> scrive.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Il nome del nome di un'origine di log eventi esistenti.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.EventSchemaTraceListener> scrive.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.TextWriterTraceListener> scrive.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Il nome del file che il <xref:System.Diagnostics.XmlWriterTraceListener> scrive.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare  **\<aggiungere >** elementi per aggiungere i listener `MyListener` e `MyEventListener` per il **listener** insieme. `MyListener`Crea un file denominato `MyListener.log` e scrive l'output del file. `MyEventListener`Crea una voce nel registro eventi.  
  
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
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Listener di traccia](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
