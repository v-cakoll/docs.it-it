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
ms.openlocfilehash: 8fedec60b6152e77d6f99bf55cf11ec909fa8f80
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2018
ms.locfileid: "48848049"
---
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="e0ab1-102">Specifica un Assembly&#39;posizione</span><span class="sxs-lookup"><span data-stu-id="e0ab1-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="e0ab1-103">Esistono due modi per specificare la posizione dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="e0ab1-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="e0ab1-104">Usando il [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="e0ab1-105">Usando il [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="e0ab1-106">È anche possibile usare la [strumento di .NET Framework Configuration (Mscorcfg. msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) per specificare i percorsi degli assembly o specificare i percorsi per common language runtime verificare la presenza di assembly.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="e0ab1-107">Uso di \<codeBase > elemento</span><span class="sxs-lookup"><span data-stu-id="e0ab1-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="e0ab1-108">È possibile usare la  **\<codeBase >** elemento solo in computer configuration o autore del file dei criteri che anche il reindirizzamento alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="e0ab1-109">Se il runtime determina la versione di assembly da usare, si applica l'impostazione di base di codice dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="e0ab1-110">Se non viene indicato alcun codice di base, il runtime esegue il probe per l'assembly in modo normale.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="e0ab1-111">Per informazioni dettagliate, vedere [modo in cui il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e0ab1-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="e0ab1-112">Nell'esempio seguente viene illustrato come specificare la posizione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="e0ab1-113">Il **versione** attributo è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly che non sono sicuro.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="e0ab1-114">Il  **\<codeBase >** elemento richiede il **href** attributo.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="e0ab1-115">Non è possibile specificare gli intervalli di versione nel  **\<codeBase >** elemento.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0ab1-116">Se viene fornito un suggerimento di base di codice per un assembly che non è sicuro, l'hint deve puntare alla base dell'applicazione o una sottodirectory della directory base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="e0ab1-117">Uso di \<probing > elemento</span><span class="sxs-lookup"><span data-stu-id="e0ab1-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="e0ab1-118">Il runtime individua gli assembly che non hanno una base di codice per l'individuazione tramite probe.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="e0ab1-119">Per altre informazioni, vedere [modo in cui il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e0ab1-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="e0ab1-120">È possibile usare la [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory il runtime ricerca durante l'individuazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="e0ab1-121">Nell'esempio seguente viene illustrato come specificare le directory che il runtime deve cercare.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="e0ab1-122">Il **privatePath** attributo contiene le directory in cui il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="e0ab1-123">Se l'applicazione si trova in c:\Programmi\Microsoft Programmi\Applicazione, il runtime cerca gli assembly che non si specificano una codebase in c:\Programmi\Microsoft Files\MyApp\Bin Files\MyApp\Bin2\Subbin c:\Programmi\Microsoft e Files\MyApp\Bin3 c:\Programmi\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="e0ab1-124">Directory specificate nella **privatePath** devono essere sottodirectory della directory base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0ab1-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ab1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0ab1-125">See Also</span></span>  
 [<span data-ttu-id="e0ab1-126">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e0ab1-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="e0ab1-127">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="e0ab1-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="e0ab1-128">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="e0ab1-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="e0ab1-129">Configurazione delle app .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0ab1-129">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
