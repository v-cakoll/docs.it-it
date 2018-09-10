---
title: Ubicazione degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d42b73d1ec20e66d604f19bb836cb7e2778e62f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505989"
---
# <a name="assembly-placement"></a><span data-ttu-id="c7006-102">Ubicazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="c7006-102">Assembly Placement</span></span>
<span data-ttu-id="c7006-103">Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso).</span><span class="sxs-lookup"><span data-stu-id="c7006-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="c7006-104">È possibile eseguire l'override del percorso usato da Common Language Runtime per cercare un assembly usando l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c7006-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="c7006-105">Se l'assembly non ha un nome sicuro, il percorso specificato tramite l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) sarà limitato alla directory dell'applicazione o a una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="c7006-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="c7006-106">Se l'assembly ha un nome sicuro l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.</span><span class="sxs-lookup"><span data-stu-id="c7006-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="c7006-107">Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="c7006-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="c7006-108">Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati.</span><span class="sxs-lookup"><span data-stu-id="c7006-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="c7006-109">Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c7006-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7006-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7006-110">See Also</span></span>  
 [<span data-ttu-id="c7006-111">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="c7006-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="c7006-112">Configurazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c7006-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="c7006-113">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="c7006-113">Advanced COM Interoperability</span></span>](https://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="c7006-114">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c7006-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
