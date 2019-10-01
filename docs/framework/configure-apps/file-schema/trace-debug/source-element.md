---
title: <source> Elemento
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: c4f7e31422ccd8129599db1120f9b0cb327d9319
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697207"
---
# <a name="source-element"></a>Elemento > \<Source
Specifica un'origine di traccia che avvia i messaggi di traccia.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<source >**  
  
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
|`switchName`|Attributo facoltativo.<br /><br /> Specifica il nome di un'istanza dell'opzione di traccia nell'applicazione. Se l'opzione non è identificata in un elemento `<switches>`, il valore specifica il livello per l'opzione.|  
|`switchType`|Attributo facoltativo.<br /><br /> Specifica il tipo di opzione di traccia. Se presente, il tipo deve essere un nome di classe valido e non può essere una stringa vuota.|  
|`extraAttribute`|Attributo facoltativo.<br /><br /> Specifica il valore per un attributo specifico dell'origine di traccia identificato dal metodo <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> per l'origine di traccia.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|Contiene i listener che raccolgono, archiviano e indirizzano i messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sources`|Contiene le origini di traccia che avviano i messaggi di traccia.|  
  
## <a name="remarks"></a>Note  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento `<source>` per aggiungere l'origine di traccia `mySource` e per impostare il livello per l'opzione di origine denominata `sourceSwitch`. Viene aggiunto un listener di traccia della console che scrive le informazioni di traccia nella console.  
  
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

- [Schema delle impostazioni di traccia e debug](index.md)
- [Opzioni di traccia](../../../debug-trace-profile/trace-switches.md)
