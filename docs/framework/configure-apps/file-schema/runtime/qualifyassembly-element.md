---
title: <qualifyAssembly> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153919"
---
# <a name="qualifyassembly-element"></a>\<elemento> qualifyAssembly
Specifica il nome completo dell'assembly da caricare in modo dinamico quando viene usato un nome parziale.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>assemblyBinding**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualificareAssembly>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`partialName`|Attributo obbligatorio.<br /><br /> Specifica il nome parziale dell'assembly così come viene visualizzato nel codice.|  
|`fullName`|Attributo obbligatorio.<br /><br /> Specifica il nome completo dell'assembly così come viene visualizzato nella Global Assembly Cache.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 La <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> chiamata al metodo utilizzando nomi di assembly parziali fa sì che Common Language Runtime cerchi l'assembly solo nella directory di base dell'applicazione. Utilizzare l'elemento ** \<>qualifyAssembly** nel file di configurazione dell'applicazione per fornire le informazioni complete sull'assembly (nome, versione, token di chiave pubblica e impostazioni cultura) e fare in modo che Common Language Runtime cerchi l'assembly nella Global Assembly Cache.  
  
 L'attributo **fullName** deve includere i quattro campi dell'identità dell'assembly: name, version, public key token e culture. L'attributo **partialName** deve fare riferimento parzialmente a un assembly. È necessario specificare almeno il nome di testo dell'assembly (il caso più comune), ma è anche possibile includere la versione, il token di chiave pubblica o le impostazioni cultura (o qualsiasi combinazione dei quattro, ma non tutti e quattro). Il **partialName** deve corrispondere al nome specificato nella chiamata. Ad esempio, non `"math"` è possibile specificare come attributo **partialName** nel file di configurazione e chiamare `Assembly.Load("math, Version=3.3.3.3")` nel codice.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`seguito la chiamata viene trasformata in modo logico in .  
  
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

- [Schema delle impostazioni di runtime](index.md)
- [Come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Riferimenti di assembly parziali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
