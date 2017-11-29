---
title: '&lt;disableCachingBindingFailures&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25d504afd7945718f08dd5f2bf92d7ea33037a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a>&lt;disableCachingBindingFailures&gt; elemento
Specifica se disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<disableCachingBindingFailures >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Non disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio. Questo è il comportamento di associazione predefinito a partire da .NET Framework versione 2.0.|  
|1|Disabilitare la memorizzazione nella cache di errori di associazione che si verificano perché l'assembly non è stato trovato il sondaggio. Questa impostazione consente di ripristinare il comportamento di associazione di .NET Framework versione 1.1.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework versione 2.0, il comportamento predefinito per il caricamento degli assembly è per memorizzare nella cache tutti i binding e gli errori di caricamento. Ovvero, se un tentativo di caricare un assembly ha esito negativo, le successive richieste per caricare l'assembly stesso non riescono immediatamente, senza tentare di individuare l'assembly. Questo elemento disabilita il comportamento predefinito per errori di associazione che si verificano perché l'assembly non è stato trovato nel percorso di sondaggio. Questi errori generano <xref:System.IO.FileNotFoundException>.  
  
 Alcuni associazione e il caricamento di errori non sono interessati da questo elemento e vengono sempre memorizzati nella cache. Questi errori si verificano perché l'assembly è stato trovato ma non può essere caricato. Generano <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>. Nell'elenco seguente è riportati alcuni esempi di tali errori.  
  
-   Se si tenta di caricare un file non è un assembly valido, i tentativi successivi di caricare l'assembly avrà esito negativo anche se il file non valido viene sostituito con l'assembly corretto.  
  
-   Se si tenta di caricare un assembly a cui è stato bloccato dal file system, i tentativi successivi di caricare l'assembly avrà esito negativo anche dopo che l'assembly viene rilasciata dal file system.  
  
-   Se uno o più versioni dell'assembly che si sta tentando di caricare è nel percorso di sondaggio, ma la versione che richiesta non è compreso tra loro, i tentativi successivi di caricare tale versione avrà esito negativo anche se la versione corretta viene spostata nel percorso di sondaggio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la memorizzazione nella cache di errori di associazione di assembly che si verificano perché l'assembly non è stato trovato il sondaggio.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
