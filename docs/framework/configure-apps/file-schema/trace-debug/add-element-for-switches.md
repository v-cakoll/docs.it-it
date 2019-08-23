---
title: Elemento <add> per <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 8fcd5cbe63a323a7509f5ff8c615364295c244d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920559"
---
# <a name="add-element-for-switches"></a>\<Aggiungi elemento > per \<le opzioni >
Specifica il livello in cui viene impostata un'opzione di traccia.  
  
 \<configuration>  
\<system.diagnostics>  
\<Opzioni >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**name**|Attributo obbligatorio.<br /><br /> Specifica il nome dell'opzione. Il valore di questo attributo corrisponde al parametro *DisplayName* passato al costruttore Switch.|  
|**value**|Attributo obbligatorio.<br /><br /> Specifica il livello dell'opzione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`switches`|Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Note  
 È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione. Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivarla o disattivarla. Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare livelli diversi per specificare i tipi di traccia o i messaggi di debug restituiti dall'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento Add >** per impostare l' `General` opzione <xref:System.Diagnostics.TraceLevel> Trace sul livello e abilitare l' `Data` opzione di traccia booleana.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Schema delle impostazioni di traccia e debug](index.md)
