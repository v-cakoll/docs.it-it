---
title: 'Procedura: Individuare assembly usando DEVPATH'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 6fa864f814d6a9ce04f2bce92c61cd0075ab5145
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912992"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="e04e4-102">Procedura: Individuare assembly usando DEVPATH</span><span class="sxs-lookup"><span data-stu-id="e04e4-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="e04e4-103">Gli sviluppatori potrebbero voler assicurarsi che un assembly condiviso che compilano funzioni correttamente con più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e04e4-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="e04e4-104">Anziché inserire continuamente l'assembly nel Global Assembly Cache durante il ciclo di sviluppo, lo sviluppatore può creare una variabile di ambiente DEVPATH che punti alla directory di output di compilazione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e04e4-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="e04e4-105">Si supponga, ad esempio, che si stia compilando un assembly condiviso denominato MySharedAssembly e che la directory di output sia C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="e04e4-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="e04e4-106">È possibile inserire C:\MySharedAssembly\Debug nella variabile DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e04e4-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="e04e4-107">È quindi necessario specificare l' [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) elemento nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="e04e4-107">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="e04e4-108">Questo elemento indica al Common Language Runtime di utilizzare DEVPATH per individuare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="e04e4-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="e04e4-109">L'assembly condiviso deve essere individuabile dal runtime.</span><span class="sxs-lookup"><span data-stu-id="e04e4-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="e04e4-110">Per specificare una directory privata per la risoluzione dei riferimenti ad assembly, utilizzare l' [ \<codeBase> elemento](./file-schema/runtime/codebase-element.md) o l' [ \<probing> elemento](./file-schema/runtime/probing-element.md) in un file di configurazione, come descritto in [specifica della posizione di un assembly](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="e04e4-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="e04e4-111">È anche possibile inserire l'assembly in una sottodirectory della directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e04e4-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="e04e4-112">Per altre informazioni, vedere [Modalità di individuazione di assembly del runtime](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e04e4-112">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e04e4-113">Si tratta di una funzionalità avanzata, destinata solo allo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e04e4-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="e04e4-114">Nell'esempio seguente viene illustrato come fare in modo che il runtime cerchi gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e04e4-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e04e4-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e04e4-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="e04e4-116">Per impostazione predefinita, questa impostazione è false.</span><span class="sxs-lookup"><span data-stu-id="e04e4-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e04e4-117">Usare questa impostazione solo in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e04e4-117">Use this setting only at development time.</span></span> <span data-ttu-id="e04e4-118">Il runtime non controlla le versioni in assembly con nome sicuro presenti in DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e04e4-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="e04e4-119">Usa semplicemente il primo assembly trovato.</span><span class="sxs-lookup"><span data-stu-id="e04e4-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04e4-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e04e4-120">See also</span></span>

- [<span data-ttu-id="e04e4-121">Configurazione delle app tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e04e4-121">Configuring Apps by using Configuration Files</span></span>](index.md)
