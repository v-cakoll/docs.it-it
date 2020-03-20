---
title: <filter>Elemento <add> per<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153453"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<filter> \<Element per \<add> for sharedListeners>
Aggiunge un filtro a un listener nella raccolta `sharedListeners`.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>sharedListeners**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di filtro**

## <a name="syntax"></a>Sintassi  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**type**|Attributo obbligatorio.<br /><br /> Specifica il tipo di filtro. È possibile utilizzare solo il nome completo del <xref:System.Type.FullName%2A?displayProperty=nameWithType> tipo (nel formato della proprietà) oppure il nome completo <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> del tipo, incluse le informazioni sull'assembly (nel formato della proprietà). Per informazioni sulla creazione di un nome di tipo completo, vedere [Specifica dei nomi](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)di tipo completi .|  
|**Initializedata**|Attributo facoltativo.<br /><br /> Stringa passata al costruttore per la classe specificata.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sharedListeners`|Raccolta di listener a cui può fare riferimento qualsiasi elemento di origine o di traccia.|  
|`add`|Aggiunge un listener alla raccolta **sharedListeners.**|  
  
## <a name="remarks"></a>Osservazioni  
 Se un listener è `<add>` definito `<sharedListeners>` in un elemento dell'elemento, il `<filter>` filtro per tale `<add>` listener deve essere definito in un elemento figlio dell'elemento.  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine.config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene `<filter>` illustrato come utilizzare l'elemento `console` per `sharedListeners` aggiungere un filtro al listener di traccia nella raccolta.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Schema delle impostazioni di traccia e debug](index.md)
