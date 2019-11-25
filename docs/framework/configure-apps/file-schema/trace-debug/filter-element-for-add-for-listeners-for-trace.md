---
title: Elemento <filter> per <add> per <listeners> per <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088898"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<> elemento del filtro per \<aggiungere > per \<listener > per \<traccia >
Aggiunge un filtro a un listener nella raccolta `Listeners` per una traccia.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**Trace**](trace-element.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**listener**](listeners-element-for-trace.md)\<
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**aggiungi >** ](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**filtro**\<

## <a name="syntax"></a>Sintassi  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`type`|Attributo obbligatorio.<br /><br /> Specifica il tipo di filtro che deve ereditare dalla classe <xref:System.Diagnostics.TraceFilter>. È possibile utilizzare il nome completo dello spazio dei nomi del tipo, che corrisponde alla proprietà <xref:System.Type.FullName%2A> del tipo, oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly, che corrisponde alla proprietà <xref:System.Type.AssemblyQualifiedName%2A>. Per informazioni sui nomi di tipo completi, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.|  
|`initializeData`|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe di filtro specificata.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`trace`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.|  
|`listeners`|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi. I listener indirizzano l'output di traccia a una destinazione appropriata.|  
|`add`|Aggiunge un listener alla raccolta `Listeners`.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<filter>` deve essere contenuto in un elemento `<add>` per un listener di traccia che specifica il tipo del listener, non solo il nome di un listener definito in un [\<sharedListeners >](sharedlisteners-element.md). Se il listener è definito in un [\<> sharedListeners](sharedlisteners-element.md), il filtro per il listener deve essere definito in tale elemento.  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento `<filter>` per aggiungere un filtro al listener `console` nell'insieme `Listeners` per Trace, specificando il livello di evento Filter come `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Schema delle impostazioni di traccia e debug](index.md)
