---
title: <assemblyBinding> (elemento) per <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eec77d4dd42a7b95d1e2cd0e353e2e54746676b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225248"
---
# <a name="assemblybinding-element-for-runtime"></a>\<assemblyBinding > (elemento) per \<runtime >
Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**xmlns**|Attributo obbligatorio.<br /><br /> Specifica lo spazio dei nomi XML necessario per il binding di assembly. Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.|  
|**appliesTo**|Specifica la versione di runtime a cui si applica il reindirizzamento di assembly .NET Framework. Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato. Se non si specifica l'attributo **appliesTo** l'elemento **\<assemblyBinding>** viene applicato a tutte le versioni di .NET Framework. Il **appliesTo** attributo è stato introdotto in .NET Framework versione 1.1; viene ignorata da .NET Framework versione 1.0. Quando si usa .NET Framework versione 1.0 vengono quindi applicati tutti gli elementi **\<assemblyBinding>** anche se viene specificato un attributo **appliesTo**.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<dependentAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Incapsula i criteri di binding e il percorso dell'assembly per ciascun assembly. Usare uno  **\<dependentAssembly >** tag per ogni assembly.|  
|[\<probing>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Specifica le sottodirectory in cui in Common Language Runtime viene effettuata la ricerca al momento del caricamento degli assembly. |  
|[\<publisherPolicy>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Specifica se il runtime applica i criteri dell'editore.|  
|[\<qualifyAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come reindirizzare una versione dell'assembly a un'altra versione e fornire un elemento codeBase.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Nell'esempio seguente viene illustrato come utilizzare il **appliesTo** attributo per reindirizzare l'associazione di un assembly .NET Framework.  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Reindirizzamento delle versioni di assembly](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
