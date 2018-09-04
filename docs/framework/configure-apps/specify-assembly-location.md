---
title: Specifica un Assembly&#39;posizione
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4a83f1e67377a5ce699301770ff0369f8f760884
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508469"
---
# <a name="specifying-an-assembly39s-location"></a>Specifica un Assembly&#39;posizione
Esistono due modi per specificare la posizione dell'assembly:  
  
-   Usando il [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.  
  
-   Usando il [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.  
  
 È anche possibile usare la [strumento di .NET Framework Configuration (Mscorcfg. msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) per specificare i percorsi degli assembly o specificare i percorsi per common language runtime verificare la presenza di assembly.  
  
## <a name="using-the-codebase-element"></a>Uso di \<codeBase > elemento  
 È possibile usare la  **\<codeBase >** elemento solo in computer configuration o autore del file dei criteri che anche il reindirizzamento alla versione dell'assembly. Se il runtime determina la versione di assembly da usare, si applica l'impostazione di base di codice dal file che determina la versione. Se non viene indicato alcun codice di base, il runtime esegue il probe per l'assembly in modo normale. Per informazioni dettagliate, vedere [modo in cui il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Nell'esempio seguente viene illustrato come specificare la posizione dell'assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Il **versione** attributo è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly che non sono sicuro. Il  **\<codeBase >** elemento richiede il **href** attributo. Non è possibile specificare gli intervalli di versione nel  **\<codeBase >** elemento.  
  
> [!NOTE]
>  Se viene fornito un suggerimento di base di codice per un assembly che non è sicuro, l'hint deve puntare alla base dell'applicazione o una sottodirectory della directory base dell'applicazione.  
  
## <a name="using-the-probing-element"></a>Uso di \<probing > elemento  
 Il runtime individua gli assembly che non hanno una base di codice per l'individuazione tramite probe. Per altre informazioni, vedere [modo in cui il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 È possibile usare la [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory il runtime ricerca durante l'individuazione di un assembly. Nell'esempio seguente viene illustrato come specificare le directory che il runtime deve cercare.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Il **privatePath** attributo contiene le directory in cui il runtime deve cercare gli assembly. Se l'applicazione si trova in c:\Programmi\Microsoft Programmi\Applicazione, il runtime cerca gli assembly che non si specificano una codebase in c:\Programmi\Microsoft Files\MyApp\Bin Files\MyApp\Bin2\Subbin c:\Programmi\Microsoft e Files\MyApp\Bin3 c:\Programmi\Microsoft. Directory specificate nella **privatePath** devono essere sottodirectory della directory base dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurazione delle app .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
