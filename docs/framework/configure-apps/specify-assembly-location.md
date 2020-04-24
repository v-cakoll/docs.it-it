---
title: Specifica della posizione di un assembly
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646028"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="d4bce-102">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="d4bce-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="d4bce-103">Esistono due modi per specificare la posizione di un assieme:</span><span class="sxs-lookup"><span data-stu-id="d4bce-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="d4bce-104">Utilizzo dell'elemento [ \<codeBase>.](./file-schema/runtime/codebase-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4bce-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="d4bce-105">Utilizzo dell'elemento [ \<>sondaggio.](./file-schema/runtime/probing-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4bce-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="d4bce-106">È inoltre possibile utilizzare [lo strumento .NET Framework Configuration (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) per specificare i percorsi degli assembly o i percorsi per Common Language Runtime di eseguire il probe degli assembly.</span><span class="sxs-lookup"><span data-stu-id="d4bce-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="d4bce-107">Utilizzo \<dell'elemento codeBase></span><span class="sxs-lookup"><span data-stu-id="d4bce-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="d4bce-108">È possibile utilizzare l'elemento \*\* \<codeBase>\*\* solo nella configurazione del computer o nei file dei criteri dell'editore che reindirizzano anche la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d4bce-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="d4bce-109">Quando il runtime determina la versione dell'assembly da utilizzare, applica l'impostazione della base di codice dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="d4bce-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="d4bce-110">Se non viene indicata alcuna base di codice, il runtime esegue il probe per l'assembly in modo normale.</span><span class="sxs-lookup"><span data-stu-id="d4bce-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="d4bce-111">Per informazioni [dettagliate,](../deployment/how-the-runtime-locates-assemblies.md)vedere Come il runtime individua gli assembly .</span><span class="sxs-lookup"><span data-stu-id="d4bce-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="d4bce-112">Nell'esempio seguente viene illustrato come specificare il percorso di un assembly.</span><span class="sxs-lookup"><span data-stu-id="d4bce-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="d4bce-113">L'attributo **version** è obbligatorio per tutti gli assembly con nome sicuro, ma deve essere omesso per gli assembly che non sono con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d4bce-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="d4bce-114">L'elemento \*\* \<codeBase>\*\* richiede l'attributo **href.**</span><span class="sxs-lookup"><span data-stu-id="d4bce-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="d4bce-115">Non è possibile specificare intervalli di versioni nell'elemento \*\* \<codeBase>.\*\*</span><span class="sxs-lookup"><span data-stu-id="d4bce-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4bce-116">Se si fornisce un suggerimento di base di codice per un assembly senza nome sicuro, l'hint deve puntare alla base dell'applicazione o a una sottodirectory della directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4bce-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="d4bce-117">Utilizzo \<dell'elemento> sondaggioUsing the sbing> Element</span><span class="sxs-lookup"><span data-stu-id="d4bce-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="d4bce-118">Il runtime individua gli assembly che non dispongono di una base di codice tramite sondaggio.</span><span class="sxs-lookup"><span data-stu-id="d4bce-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="d4bce-119">Per ulteriori informazioni sul sondaggio, vedere [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d4bce-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="d4bce-120">È possibile utilizzare l'elemento [ \<>sondaggio](./file-schema/runtime/probing-element.md) nel file di configurazione dell'applicazione per specificare le sottodirectory in cui il runtime deve eseguire la ricerca durante l'individuazione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="d4bce-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="d4bce-121">Nell'esempio seguente viene illustrato come specificare le directory in cui il runtime deve eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4bce-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d4bce-122">L'attributo **privatePath** contiene le directory in cui il runtime deve cercare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="d4bce-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="d4bce-123">Se l'applicazione si trova nel percorso C:, Programmi, MyApp, il runtime cercherà gli assembly che non specificano una base di codice in C:.</span><span class="sxs-lookup"><span data-stu-id="d4bce-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="d4bce-124">Le directory specificate in **privatePath** devono essere sottodirectory della directory di base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4bce-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bce-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4bce-125">See also</span></span>

- [<span data-ttu-id="d4bce-126">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="d4bce-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="d4bce-127">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="d4bce-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="d4bce-128">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="d4bce-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="d4bce-129">Configurazione delle app tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d4bce-129">Configuring Apps by using Configuration Files</span></span>](index.md)
