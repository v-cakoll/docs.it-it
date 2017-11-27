---
title: '&lt;asserzione&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 520dfec180157c9a05c5fc3beb51b5fc17f9088b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltassertgt-element"></a>&lt;asserzione&gt; elemento
Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.  
  
 \<configuration>  
\<System. Diagnostics >  
\<Assert >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`assertuienabled`|Attributo facoltativo.<br /><br /> Specifica se visualizzare un finestra di messaggio quando il **debug. Assert** restituisce metodo **false**.|  
|`logfilename`|Attributo facoltativo.<br /><br /> Specifica il nome del file in cui scrivere il messaggio se **debug. Assert** restituisce **false**.|  
  
## <a name="assertuienabled-attribute"></a>Attributo AssertUiEnabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Consente di visualizzare la finestra di messaggio. Questa è l'impostazione predefinita.|  
|`false`|Non viene visualizzata la finestra di messaggio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Note  
 Entrambi gli attributi di  **\<assert >** elemento sono facoltativi. È possibile disabilitare le finestre di messaggio senza specificare un file per scrivere i messaggi oppure è possibile specificare un file per lasciando attivate le finestre di messaggio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la visualizzazione di finestre di messaggio quando si chiama **debug. Assert** e scrivere i messaggi `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Diagnostics.Debug>  
 [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
