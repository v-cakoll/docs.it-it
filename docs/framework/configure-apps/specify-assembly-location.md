---
title: Specifica un Assembly&#39;percorso s
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 65bd075115e33486e86e8081b01b96db665e9da5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758269"
---
# <a name="specifying-an-assembly39s-location"></a>Specifica un Assembly&#39;percorso s
Esistono due modi per specificare il percorso dell'assembly:  
  
-   Utilizzo di [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.  
  
-   Utilizzo di [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.  
  
 È inoltre possibile utilizzare il [strumento .NET Framework Configuration (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) per specificare i percorsi degli assembly o percorsi visualizzati per common language runtime verificare la presenza di assembly.  
  
## <a name="using-the-codebase-element"></a>Utilizzo di \<codeBase > elemento  
 È possibile utilizzare il  **\<codeBase >** elemento solo nei computer server di pubblicazione o di configurazione file dei criteri che anche la versione dell'assembly di reindirizzamento. Quando il runtime determina la versione di assembly da usare, si applica l'impostazione di base del codice dal file che determina la versione. Se non viene specificata alcuna base di codice, il runtime verifica per l'assembly in modo normale. Per informazioni dettagliate, vedere [come il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Nell'esempio seguente viene illustrato come specificare il percorso di un assembly.  
  
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
  
 Il **versione** attributo è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly senza nome sicuro. Il  **\<codeBase >** elemento richiede il **href** attributo. Non è possibile specificare gli intervalli di versione nel  **\<codeBase >** elemento.  
  
> [!NOTE]
>  Se viene fornito un hint di base di codice per un assembly che non è sicuro, l'hint deve puntare alla base dell'applicazione o una sottodirectory della directory base dell'applicazione.  
  
## <a name="using-the-probing-element"></a>Utilizzo di \<probing > elemento  
 Il runtime individua gli assembly che non contengono un codice di base mediante la ricerca. Per ulteriori informazioni, vedere [come il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 È possibile utilizzare il [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory, eseguire la ricerca durante l'individuazione di un assembly. Nell'esempio seguente viene illustrato come specificare directory di cui che eseguire la ricerca.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Il **privatePath** attributo contiene le directory che il runtime deve cercare gli assembly. Se l'applicazione si trova in c:\Programmi\Microsoft Programmi\Applicazione, il runtime cerca gli assembly che non si specificano una base di codice in c:\Programmi\Microsoft Files\MyApp\Bin Files\MyApp\Bin2\Subbin c:\Programmi\Microsoft e c:\Programmi\Microsoft Files\MyApp\Bin3. Directory specificate in **privatePath** devono essere sottodirectory della directory base dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurazione di App .NET Framework](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
