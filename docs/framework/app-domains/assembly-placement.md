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
ms.openlocfilehash: 829aa80169319b67a8cc5ee39fee9214cd4fcbce
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971634"
---
# <a name="assembly-placement"></a><span data-ttu-id="dd33f-102">Ubicazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="dd33f-102">Assembly Placement</span></span>
<span data-ttu-id="dd33f-103">Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso).</span><span class="sxs-lookup"><span data-stu-id="dd33f-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="dd33f-104">È possibile eseguire l'override del percorso usato da Common Language Runtime per cercare un assembly usando l'elemento [\<codeBase>](../../framework/configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dd33f-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="dd33f-105">Se l'assembly non ha un nome sicuro, il percorso specificato tramite l'elemento [\<codeBase>](../../framework/configure-apps/file-schema/runtime/codebase-element.md) sarà limitato alla directory dell'applicazione o a una sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="dd33f-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="dd33f-106">Se l'assembly ha un nome sicuro l'elemento [\<codeBase>](../../framework/configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.</span><span class="sxs-lookup"><span data-stu-id="dd33f-106">If the assembly has a strong name, the [\<codeBase> Element](../../framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="dd33f-107">Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="dd33f-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="dd33f-108">Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati.</span><span class="sxs-lookup"><span data-stu-id="dd33f-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="dd33f-109">Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dd33f-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd33f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd33f-110">See also</span></span>

- [<span data-ttu-id="dd33f-111">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="dd33f-111">How the Runtime Locates Assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="dd33f-112">Configurazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="dd33f-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="dd33f-113">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="dd33f-113">Interoperating with unmanaged code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="dd33f-114">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="dd33f-114">Assemblies in .NET</span></span>](index.md)
