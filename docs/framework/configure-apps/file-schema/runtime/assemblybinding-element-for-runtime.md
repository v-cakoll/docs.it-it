---
title: Elemento <assemblyBinding> per <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154322"
---
# <a name="assemblybinding-element-for-runtime"></a>Elemento \<assemblyBinding> per \<runtime>
Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
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
|**appliesTo**|Specifica la versione di runtime a cui si applica il reindirizzamento di assembly .NET Framework. Questo attributo facoltativo usa un numero di versione di .NET Framework per indicare la versione a cui deve essere applicato. Se non è specificato alcun attributo **appliesTo** , l' **\<assemblyBinding>** elemento si applica a tutte le versioni del .NET Framework. L'attributo **appliesTo** è stato introdotto nella versione .NET Framework 1,1; viene ignorato dalla versione di .NET Framework 1,0. Ciò significa che tutti **\<assemblyBinding>** gli elementi vengono applicati quando si usa la versione di .NET Framework 1,0, anche se viene specificato un attributo **appliesTo** .|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|Incapsula i criteri di binding e il percorso dell'assembly per ciascun assembly. Usare un **\<dependentAssembly>** tag per ogni assembly.|  
|[\<probing>](probing-element.md)|Specifica le sottodirectory in cui in Common Language Runtime viene effettuata la ricerca al momento del caricamento degli assembly. |  
|[\<publisherPolicy>](publisherpolicy-element.md)|Specifica se il runtime applica i criteri dell'editore.|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.|  
  
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
  
 Nell'esempio seguente viene illustrato come utilizzare l'attributo **appliesTo** per reindirizzare l'associazione di un assembly .NET Framework.  
  
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
  
## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [Reindirizzamento delle versioni di assembly](../../redirect-assembly-versions.md)
