---
title: 'Procedura: individuare assembly mediante DEVPATH'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ee4200a67ef9d9d123be3bc32b02ac61512d23b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="6f6d5-102">Procedura: individuare assembly mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="6f6d5-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="6f6d5-103">Gli sviluppatori desiderano assicurarsi che funzioni correttamente in un assembly condiviso che viene compilato con più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="6f6d5-104">Anziché inserire continuamente l'assembly nella global assembly cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punta alla directory di output di compilazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="6f6d5-105">Ad esempio, si supponga che si compila un assembly condiviso denominato MySharedAssembly e la directory di output è C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="6f6d5-106">È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="6f6d5-107">È quindi necessario specificare il [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="6f6d5-108">Questo elemento indica a common language runtime utilizza la variabile DEVPATH per individuare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="6f6d5-109">L'assembly condiviso deve essere individuabile dal runtime.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="6f6d5-110">Per specificare una cartella privata per la risoluzione dei riferimenti agli assembly, utilizzare il [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [Specificando il percorso di un Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="6f6d5-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="6f6d5-111">È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="6f6d5-112">Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="6f6d5-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f6d5-113">Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="6f6d5-114">Nell'esempio seguente viene illustrato come impostare il runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f6d5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f6d5-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6f6d5-116">L'impostazione predefinita è false.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f6d5-117">Utilizzare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-117">Use this setting only at development time.</span></span> <span data-ttu-id="6f6d5-118">Il runtime non controllate le versioni degli assembly con nome sicuro, vedere il DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="6f6d5-119">Usa semplicemente il primo assembly individuato.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f6d5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f6d5-120">See Also</span></span>  
 [<span data-ttu-id="6f6d5-121">Configurazione delle app .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f6d5-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
