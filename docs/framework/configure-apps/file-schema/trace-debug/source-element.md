---
title: '&lt;origine&gt; elemento'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 818324077322fffb40a192c9197efde6e8ff7591
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088945"
---
# <a name="ltsourcegt-element"></a>&lt;origine&gt; elemento
Specifica un'origine di traccia che avvia i messaggi di traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
\<origini >  
\<origine >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo facoltativo.<br /><br /> Specifica il nome dell'origine di traccia.|  
|`switchName`|Attributo facoltativo.<br /><br /> Specifica il nome di un'istanza del commutatore traccia nell'applicazione. Se l'opzione non viene identificata una `<switches>` elemento, il valore specifica il livello per il commutatore.|  
|`switchType`|Attributo facoltativo.<br /><br /> Specifica il tipo di opzione di traccia. Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.|  
|`extraAttribute`|Attributo facoltativo.<br /><br /> Specifica il valore per un attributo specifico dell'origine di traccia identificato dalla <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> metodo per l'origine di traccia.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sources`|Contiene le origini di traccia che avviano i messaggi di traccia.|  
  
## <a name="remarks"></a>Note  
 Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<source>` elemento a cui aggiungere l'origine di traccia `mySource` e impostare il livello per l'opzione di origine denominata `sourceSwitch`. Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Opzioni di traccia](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
