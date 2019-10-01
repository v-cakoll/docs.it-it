---
title: <switches> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: c161f842192396101dcc6850f3b3da328958eac3
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697092"
---
# <a name="switches-element"></a>Elemento > \<switches
Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<switches >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|Specifica il livello in cui viene impostata un'opzione di traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`System.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Note  
 È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione. Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivarla o disattivarla. Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare livelli diversi per specificare i tipi di traccia o i messaggi di debug restituiti dall'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<switch** per impostare l'opzione di traccia `General` sul livello <xref:System.Diagnostics.TraceLevel> e abilitare l'opzione di traccia booleana `Data`.  
  
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
 