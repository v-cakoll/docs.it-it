---
title: Ubicazione degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 5eb7b5c35bb40d5a58390ccbd4619cbed4e06c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119963"
---
# <a name="assembly-placement"></a><span data-ttu-id="6aaeb-102">Ubicazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="6aaeb-102">Assembly Placement</span></span>
<span data-ttu-id="6aaeb-103">Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso).</span><span class="sxs-lookup"><span data-stu-id="6aaeb-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="6aaeb-104">È possibile eseguire l'override della posizione in cui il Common Language Runtime cerca un assembly usando l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="6aaeb-105">Se l'assembly non ha un nome sicuro, il percorso specificato tramite l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) è limitato alla directory dell'applicazione o a una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="6aaeb-106">Se l'assembly ha un nome sicuro, l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-106">If the assembly has a strong name, the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="6aaeb-107">Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="6aaeb-108">Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="6aaeb-109">Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6aaeb-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aaeb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aaeb-110">See also</span></span>

- [<span data-ttu-id="6aaeb-111">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="6aaeb-111">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6aaeb-112">Configurazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6aaeb-112">Configuring Apps</span></span>](../configure-apps/index.md)
- [<span data-ttu-id="6aaeb-113">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="6aaeb-113">Interoperating with unmanaged code</span></span>](../interop/index.md)
- [<span data-ttu-id="6aaeb-114">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="6aaeb-114">Assemblies in .NET</span></span>](index.md)
