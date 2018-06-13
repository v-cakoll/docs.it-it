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
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="e432a-102">Specifica un Assembly&#39;percorso s</span><span class="sxs-lookup"><span data-stu-id="e432a-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="e432a-103">Esistono due modi per specificare il percorso dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="e432a-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="e432a-104">Utilizzo di [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e432a-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="e432a-105">Utilizzo di [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e432a-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="e432a-106">È inoltre possibile utilizzare il [strumento .NET Framework Configuration (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) per specificare i percorsi degli assembly o percorsi visualizzati per common language runtime verificare la presenza di assembly.</span><span class="sxs-lookup"><span data-stu-id="e432a-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="e432a-107">Utilizzo di \<codeBase > elemento</span><span class="sxs-lookup"><span data-stu-id="e432a-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="e432a-108">È possibile utilizzare il  **\<codeBase >** elemento solo nei computer server di pubblicazione o di configurazione file dei criteri che anche la versione dell'assembly di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e432a-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="e432a-109">Quando il runtime determina la versione di assembly da usare, si applica l'impostazione di base del codice dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="e432a-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="e432a-110">Se non viene specificata alcuna base di codice, il runtime verifica per l'assembly in modo normale.</span><span class="sxs-lookup"><span data-stu-id="e432a-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="e432a-111">Per informazioni dettagliate, vedere [come il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e432a-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="e432a-112">Nell'esempio seguente viene illustrato come specificare il percorso di un assembly.</span><span class="sxs-lookup"><span data-stu-id="e432a-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="e432a-113">Il **versione** attributo è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly senza nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e432a-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="e432a-114">Il  **\<codeBase >** elemento richiede il **href** attributo.</span><span class="sxs-lookup"><span data-stu-id="e432a-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="e432a-115">Non è possibile specificare gli intervalli di versione nel  **\<codeBase >** elemento.</span><span class="sxs-lookup"><span data-stu-id="e432a-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e432a-116">Se viene fornito un hint di base di codice per un assembly che non è sicuro, l'hint deve puntare alla base dell'applicazione o una sottodirectory della directory base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e432a-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="e432a-117">Utilizzo di \<probing > elemento</span><span class="sxs-lookup"><span data-stu-id="e432a-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="e432a-118">Il runtime individua gli assembly che non contengono un codice di base mediante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e432a-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="e432a-119">Per ulteriori informazioni, vedere [come il Runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e432a-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="e432a-120">È possibile utilizzare il [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory, eseguire la ricerca durante l'individuazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="e432a-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="e432a-121">Nell'esempio seguente viene illustrato come specificare directory di cui che eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e432a-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="e432a-122">Il **privatePath** attributo contiene le directory che il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="e432a-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="e432a-123">Se l'applicazione si trova in c:\Programmi\Microsoft Programmi\Applicazione, il runtime cerca gli assembly che non si specificano una base di codice in c:\Programmi\Microsoft Files\MyApp\Bin Files\MyApp\Bin2\Subbin c:\Programmi\Microsoft e c:\Programmi\Microsoft Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="e432a-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="e432a-124">Directory specificate in **privatePath** devono essere sottodirectory della directory base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e432a-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e432a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e432a-125">See Also</span></span>  
 [<span data-ttu-id="e432a-126">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e432a-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="e432a-127">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="e432a-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="e432a-128">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="e432a-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="e432a-129">Configurazione di App .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e432a-129">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
