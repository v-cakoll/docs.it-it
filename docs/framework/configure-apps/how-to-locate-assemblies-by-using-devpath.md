---
title: 'Procedura: individuare assembly mediante DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3a9ae9c60ad7de80d04f16984b3b2fb048421cc2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080288"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="3dac4-102">Procedura: individuare assembly mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="3dac4-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="3dac4-103">Gli sviluppatori desiderano assicurarsi che funzioni correttamente un assembly condiviso in corso di sviluppo con più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3dac4-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="3dac4-104">Anziché inserire continuamente l'assembly nella global assembly cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punta alla directory di output di compilazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3dac4-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="3dac4-105">Ad esempio, si supponga che si sta creando un assembly condiviso denominato MySharedAssembly e la directory di output è C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="3dac4-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="3dac4-106">È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="3dac4-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="3dac4-107">È quindi necessario specificare il [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="3dac4-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="3dac4-108">Questo elemento indica a common language runtime da usare DEVPATH per individuare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="3dac4-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="3dac4-109">L'assembly condiviso deve essere individuabile dal runtime.</span><span class="sxs-lookup"><span data-stu-id="3dac4-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="3dac4-110">Per specificare una cartella privata per la risoluzione dei riferimenti agli assembly, utilizzare il [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oppure [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [Che specifica la posizione dell'Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="3dac4-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="3dac4-111">È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3dac4-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="3dac4-112">Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3dac4-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dac4-113">Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3dac4-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="3dac4-114">Nell'esempio seguente viene illustrato come parte del runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="3dac4-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dac4-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dac4-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="3dac4-116">L'impostazione predefinita è false.</span><span class="sxs-lookup"><span data-stu-id="3dac4-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dac4-117">Usare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3dac4-117">Use this setting only at development time.</span></span> <span data-ttu-id="3dac4-118">Il runtime non verifica se le versioni di assembly con nome sicuro trovato nel DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="3dac4-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="3dac4-119">Utilizza semplicemente il primo assembly individuato.</span><span class="sxs-lookup"><span data-stu-id="3dac4-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dac4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dac4-120">See Also</span></span>  
 [<span data-ttu-id="3dac4-121">Configurazione delle app .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3dac4-121">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
