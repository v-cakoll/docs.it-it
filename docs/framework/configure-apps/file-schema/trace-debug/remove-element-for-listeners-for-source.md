---
title: '&lt;rimuovere&gt; elemento per &lt;listener&gt; per &lt;origine&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b983c5eb80f958098b6991970559d077b97a0759
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;rimuovere&gt; elemento per &lt;listener&gt; per &lt;origine&gt;
Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
\<origini >  
\<origine >  
\<listener >  
\<rimuovere >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Il nome del listener da rimuovere il `Listeners` insieme.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sources`|Contiene le origini di traccia che avviano i messaggi di traccia.|  
|`source`|Specifica un'origine di traccia che avvia i messaggi di traccia.|  
|`listeners`|Specifica i listener di raccolgano, archiviano e indirizzare i messaggi.|  
  
## <a name="remarks"></a>Note  
 Il `<remove>` elemento consente di rimuovere un listener specificato dal `Listeners` insieme per un'origine di traccia.  
  
 È possibile rimuovere un elemento il `Listeners` insieme per un'origine di traccia a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> metodo il <xref:System.Diagnostics.TraceSource.Listeners%2A> proprietà del <xref:System.Diagnostics.TraceSource> istanza.  
  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<remove>` elemento prima di utilizzare il `<add>` elemento per aggiungere il listener `console` per il `Listeners` raccolta per l'origine di traccia `TraceSourceApp`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [Listener di traccia](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
