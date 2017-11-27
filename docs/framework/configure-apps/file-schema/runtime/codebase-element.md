---
title: '&lt;codeBase&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c5b30f1dc3ccade3028c31c57ffdab521802f086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcodebasegt-element"></a>&lt;codeBase&gt; elemento
Specifica se common language runtime può individuare un assembly.  
  
 \<configuration>  
\<runtime >  
\<assemblyBinding >  
\<dependentAssembly >  
\<codeBase >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`href`|Attributo obbligatorio.<br /><br /> Specifica l'URL in cui il runtime può individuare la versione specificata dell'assembly.|  
|`version`|Attributo obbligatorio.<br /><br /> Specifica la versione dell'assembly che viene applicata la codebase. Il formato di un numero di versione di assembly è *revisione*.|  
  
## <a name="version-attribute"></a>Attributo di versione  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.|Non applicabile.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`buildproviders`|Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati. Possono essere presenti più provider di compilazione.|  
|`compilation`|Consente di configurare tutte le impostazioni di compilazione che utilizza ASP.NET.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`System.web`|Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.|  
  
## <a name="remarks"></a>Note  
 Per il runtime di utilizzare il  **\<codeBase >** impostato in un file di configurazione di computer o un file dei criteri editore, il file deve reindirizzare la versione dell'assembly. File di configurazione dell'applicazione possono avere un'impostazione di codebase senza eseguire il reindirizzamento alla versione dell'assembly. Dopo aver determinato la versione di assembly da utilizzare, il runtime applica l'impostazione della codebase dal file che determina la versione. Se non è indicato alcun codebase, il runtime verifica per l'assembly nel modo consueto.  
  
 Se l'assembly dispone di un nome sicuro, l'impostazione della codebase può essere in un punto qualsiasi nella rete intranet locale o Internet. Se l'assembly è un assembly privato, l'impostazione di codebase deve essere un percorso relativo alla directory dell'applicazione.  
  
 Per gli assembly senza nome sicuro, la versione viene ignorata e il caricatore Usa la prima occorrenza di \<codebase > all'interno di \<dependentAssembly >. Se c'è una voce nel file di configurazione dell'applicazione che reindirizza l'associazione a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare in cui il runtime può individuare un assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Specifica della posizione di un assembly](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
