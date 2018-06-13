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
manager: markl
ms.openlocfilehash: 918acf069c63d3aa8187f0f04e1f6c55ec961458
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755461"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="b5da1-102">Procedura: individuare assembly mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="b5da1-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="b5da1-103">Gli sviluppatori desiderano assicurarsi che funzioni correttamente in un assembly condiviso che viene compilato con più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b5da1-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="b5da1-104">Anziché inserire continuamente l'assembly nella global assembly cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punta alla directory di output di compilazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b5da1-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="b5da1-105">Ad esempio, si supponga che si compila un assembly condiviso denominato MySharedAssembly e la directory di output è C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="b5da1-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="b5da1-106">È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b5da1-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="b5da1-107">È quindi necessario specificare il [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="b5da1-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="b5da1-108">Questo elemento indica a common language runtime utilizza la variabile DEVPATH per individuare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="b5da1-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="b5da1-109">L'assembly condiviso deve essere individuabile dal runtime.</span><span class="sxs-lookup"><span data-stu-id="b5da1-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="b5da1-110">Per specificare una cartella privata per la risoluzione dei riferimenti agli assembly, utilizzare il [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [Specificando il percorso di un Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="b5da1-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="b5da1-111">È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5da1-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="b5da1-112">Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b5da1-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5da1-113">Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b5da1-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="b5da1-114">Nell'esempio seguente viene illustrato come impostare il runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b5da1-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5da1-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5da1-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b5da1-116">L'impostazione predefinita è false.</span><span class="sxs-lookup"><span data-stu-id="b5da1-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5da1-117">Utilizzare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b5da1-117">Use this setting only at development time.</span></span> <span data-ttu-id="b5da1-118">Il runtime non controllate le versioni degli assembly con nome sicuro, vedere il DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="b5da1-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="b5da1-119">Usa semplicemente il primo assembly individuato.</span><span class="sxs-lookup"><span data-stu-id="b5da1-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5da1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5da1-120">See Also</span></span>  
 [<span data-ttu-id="b5da1-121">Configurazione di App .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b5da1-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
