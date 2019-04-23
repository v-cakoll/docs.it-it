---
title: <disableCachingBindingFailures> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4893adaf528f1a9ef8fc8eab8027406fd8520cc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159276"
---
# <a name="disablecachingbindingfailures-element"></a>\<disableCachingBindingFailures > elemento
Specifica se disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<disableCachingBindingFailures>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Non disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione. Questo è il comportamento predefinito dell'associazione a partire da .NET Framework versione 2.0.|  
|1|Disabilitare la memorizzazione nella cache degli errori che si verificano perché l'assembly non è stato trovato il sondaggio di associazione. Questa impostazione consente di ripristinare il comportamento di associazione di .NET Framework versione 1.1.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework versione 2.0, il comportamento predefinito per il caricamento degli assembly è per memorizzare nella cache tutti i binding e gli errori di caricamento. Vale a dire, se non riesce un tentativo di caricare un assembly, le successive richieste per caricare l'assembly stesso immediatamente esito negativo, senza tentare di individuare l'assembly. Questo elemento consente di disattivare il comportamento predefinito per gli errori che si verificano perché l'assembly non è stato trovato nel percorso di sondaggio di associazione. Questi errori generano <xref:System.IO.FileNotFoundException>.  
  
 Associazione di alcuni errori di caricamento non sono interessati da questo elemento e vengono sempre memorizzati nella cache. Questi errori si verificano perché l'assembly è stato trovato ma non può essere caricato. Generano <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>. Nell'elenco seguente sono riportati alcuni esempi di tali errori.  
  
-   Se si tenta di caricare un file non è un assembly valido, i tentativi successivi per caricare l'assembly avrà esito negativo anche se il file non valido viene sostituito con l'assembly corretto.  
  
-   Se si tenta di caricare un assembly che è stato bloccato dal file system, i tentativi successivi per caricare l'assembly avrà esito negativo anche dopo che l'assembly viene rilasciata dal file system.  
  
-   Se uno o più versioni dell'assembly che si sta tentando di caricare è nel percorso di sondaggio, ma la versione specifica di che richiesta non è tra di essi, i tentativi successivi di caricare tale versione avrà esito negativo anche se la versione corretta verrà spostata nel percorso di sondaggio.  
  
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

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
