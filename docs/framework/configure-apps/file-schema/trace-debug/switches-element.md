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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153230"
---
# <a name="switches-element"></a>\<interruttori> Elemento
Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.diagnostics**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<interruttori>**

## <a name="syntax"></a>Sintassi  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<aggiungere>](add-element-for-switches.md)|Specifica il livello in cui viene impostata un'opzione di traccia.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`System.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione. Se l'interruttore è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivarlo e disattivarlo. Se l'opzione <xref:System.Diagnostics.TraceSwitch>è un oggetto , è possibile assegnarvi livelli diversi per specificare i tipi di messaggi di traccia o di debug restituiti dall'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare `General` <xref:System.Diagnostics.TraceLevel> `Data` ** \<l'opzione>** elemento per impostare l'opzione di traccia sul livello e abilitare l'opzione di traccia booleana.  
  
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
