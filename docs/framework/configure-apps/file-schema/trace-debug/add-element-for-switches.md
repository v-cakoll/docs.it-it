---
title: '&lt;aggiungere&gt; elemento per &lt;switch&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: de1acb37f3236598e9d8a74a188033d18b65ac8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a>&lt;aggiungere&gt; elemento per &lt;switch&gt;
Specifica il livello in cui viene impostata un'opzione di traccia.  
  
 \<configuration>  
\<System. Diagnostics >  
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
|**name**|Attributo obbligatorio.<br /><br /> Specifica il nome del commutatore. Il valore di questo attributo corrisponde alla *displayName* parametro passato al costruttore di opzioni.|  
|**value**|Attributo obbligatorio.<br /><br /> Specifica il livello del commutatore.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`switches`|Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Note  
 È possibile modificare il livello di un'opzione di traccia mediante l'inserimento in un file di configurazione. Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivare e disattivare. Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare diversi livelli per specificare i tipi di traccia messaggi o di debug generati dall'applicazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il  **\<aggiungere >** elemento da impostare il `General` opzione di traccia di <xref:System.Diagnostics.TraceLevel> livello e attivare il `Data` opzione di traccia Boolean.  
  
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
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
