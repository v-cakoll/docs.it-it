---
title: '&lt;qualifyAssembly&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dd24ae9e5659deff7ddbe4183c70d5b442542cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltqualifyassemblygt-element"></a>&lt;qualifyAssembly&gt; elemento
Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<qualifyAssembly>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`partialName`|Attributo obbligatorio.<br /><br /> Specifica il nome parziale dell'assembly come appare nel codice.|  
|`fullName`|Attributo obbligatorio.<br /><br /> Specifica il nome completo dell'assembly come appare nella global assembly cache.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 La chiamata di <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metodo utilizzando nomi di assembly parziali fa sì che common language runtime cercare l'assembly solo nella directory base dell'applicazione. Utilizzare il  **\<qualifyAssembly >** elemento nel file di configurazione dell'applicazione per informazioni sull'assembly (nome, versione, token di chiave pubblica e impostazioni cultura) e causare common language runtime per la ricerca per l'assembly nella global assembly cache.  
  
 Il **fullName** attributo deve includere i quattro campi relativi all'identità dell'assembly: nome, versione, token di chiave pubblica e impostazioni cultura. Il **partialName** attributo parzialmente deve fare riferimento a un assembly. È necessario specificare almeno il nome dell'assembly testo (il caso più comune), ma è anche possibile includere una versione, token di chiave pubblica o delle impostazioni cultura (o qualsiasi combinazione di quattro, ma non tutti e quattro). Il **partialName** deve corrispondere al nome specificato nella chiamata. Ad esempio, è possibile specificare `"math"` come il **partialName** attributo nel file di configurazione e chiamare `Assembly.Load("math, Version=3.3.3.3")` nel codice.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene logicamente la chiamata `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Come il runtime individua gli assembly](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [NIB: I riferimenti di Assembly parziali](http://msdn.microsoft.com/library/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
