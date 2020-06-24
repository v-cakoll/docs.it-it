---
title: Specifica della posizione di un assembly
description: Vedere come specificare il percorso di un assembly in .NET usando l'elemento codebase o l'elemento probe in un file di configurazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: e14bdc12598d0aa6cdd2789b09a04ab8ed134169
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141704"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="bbc75-103">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="bbc75-103">Specifying an Assembly's Location</span></span>
<span data-ttu-id="bbc75-104">È possibile specificare la posizione di un assembly in due modi:</span><span class="sxs-lookup"><span data-stu-id="bbc75-104">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="bbc75-105">Utilizzando l' [\<codeBase>](./file-schema/runtime/codebase-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbc75-105">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="bbc75-106">Utilizzando l' [\<probing>](./file-schema/runtime/probing-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbc75-106">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="bbc75-107">È anche possibile usare lo [strumento di configurazione .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) per specificare i percorsi degli assembly o specificare i percorsi per il Common Language Runtime per eseguire il probe degli assembly.</span><span class="sxs-lookup"><span data-stu-id="bbc75-107">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="bbc75-108">Utilizzo dell' \<codeBase> elemento</span><span class="sxs-lookup"><span data-stu-id="bbc75-108">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="bbc75-109">È possibile usare l' **\<codeBase>** elemento solo nei file di configurazione del computer o dei criteri dell'editore che reindirizzano anche la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bbc75-109">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="bbc75-110">Quando il runtime determina la versione dell'assembly da usare, applica l'impostazione codebase dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="bbc75-110">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="bbc75-111">Se non è indicata alcuna codebase, il runtime esegue il probe per l'assembly in modo normale.</span><span class="sxs-lookup"><span data-stu-id="bbc75-111">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="bbc75-112">Per informazioni dettagliate, vedere [come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bbc75-112">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="bbc75-113">Nell'esempio seguente viene illustrato come specificare la posizione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="bbc75-113">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="bbc75-114">L'attributo **Version** è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="bbc75-114">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="bbc75-115">L' **\<codeBase>** elemento richiede l'attributo **href** .</span><span class="sxs-lookup"><span data-stu-id="bbc75-115">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="bbc75-116">Non è possibile specificare gli intervalli di versione nell' **\<codeBase>** elemento.</span><span class="sxs-lookup"><span data-stu-id="bbc75-116">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbc75-117">Se si fornisce un hint codebase per un assembly senza nome sicuro, l'hint deve puntare alla base dell'applicazione o a una sottodirectory della directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bbc75-117">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="bbc75-118">Utilizzo dell' \<probing> elemento</span><span class="sxs-lookup"><span data-stu-id="bbc75-118">Using the \<probing> Element</span></span>  
 <span data-ttu-id="bbc75-119">Il runtime individua gli assembly che non dispongono di una codebase tramite sondaggio.</span><span class="sxs-lookup"><span data-stu-id="bbc75-119">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="bbc75-120">Per altre informazioni sul sondaggio, vedere [come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="bbc75-120">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="bbc75-121">È possibile utilizzare l' [\<probing>](./file-schema/runtime/probing-element.md) elemento nel file di configurazione dell'applicazione per specificare le sottodirectory in cui il runtime deve eseguire la ricerca durante l'individuazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="bbc75-121">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="bbc75-122">Nell'esempio seguente viene illustrato come specificare le directory in cui eseguire la ricerca del runtime.</span><span class="sxs-lookup"><span data-stu-id="bbc75-122">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bbc75-123">L'attributo **privatePath** contiene le directory che il runtime deve cercare per gli assembly.</span><span class="sxs-lookup"><span data-stu-id="bbc75-123">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="bbc75-124">Se l'applicazione si trova in C:\Program C:\Programmi\MyApp, il runtime cercherà gli assembly che non specificano una codebase in C:\Program C:\Programmi\MyApp\Bin, C:\Program C:\Programmi\MyApp\Bin2\Subbin e C:\Program C:\Programmi\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="bbc75-124">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="bbc75-125">Le directory specificate in **privatePath** devono essere sottodirectory della directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bbc75-125">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc75-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbc75-126">See also</span></span>

- [<span data-ttu-id="bbc75-127">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="bbc75-127">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bbc75-128">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="bbc75-128">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bbc75-129">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="bbc75-129">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bbc75-130">Configurazione delle app tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bbc75-130">Configuring Apps by using Configuration Files</span></span>](index.md)
