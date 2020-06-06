---
title: <remove>Elemento per <listeners> per<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153335"
---
# <a name="remove-element-for-listeners-for-source"></a>\<remove>Elemento per \<listeners> per\<source>
Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`name`|Attributo obbligatorio.<br /><br /> Nome del listener da rimuovere dalla `Listeners` raccolta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
|`sources`|Contiene le origini di traccia che avviano i messaggi di traccia.|  
|`source`|Specifica un'origine di traccia che avvia i messaggi di traccia.|  
|`listeners`|Specifica i listener che raccolgono, archiviano e indirizzano i messaggi.|  
  
## <a name="remarks"></a>Commenti  
 L' `<remove>` elemento rimuove un listener specificato dalla `Listeners` raccolta per un'origine di traccia.  
  
 È possibile rimuovere un elemento dalla `Listeners` raccolta per un'origine di traccia a livello di codice chiamando il <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> Metodo sulla <xref:System.Diagnostics.TraceSource.Listeners%2A> proprietà dell' <xref:System.Diagnostics.TraceSource> istanza.  
  
 Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l' `<remove>` elemento prima di utilizzare l' `<add>` elemento per aggiungere il listener `console` alla `Listeners` raccolta per l'origine di traccia `TraceSourceApp` .  
  
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Schema delle impostazioni di traccia e debug](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [Listener di traccia](../../../debug-trace-profile/trace-listeners.md)
