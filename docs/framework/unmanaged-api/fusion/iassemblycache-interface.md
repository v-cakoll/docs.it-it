---
title: Interfaccia IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157cc9f5f520f376c0c055ab49b116bc7961f421
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641070"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="703d5-102">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="703d5-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="703d5-103">Rappresenta la global assembly cache per l'uso con la tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="703d5-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="703d5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="703d5-104">Methods</span></span>  
  
|<span data-ttu-id="703d5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="703d5-105">Method</span></span>|<span data-ttu-id="703d5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="703d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="703d5-107">Metodo CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="703d5-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="703d5-108">Ottiene un riferimento a una nuova [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="703d5-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="703d5-109">Metodo CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="703d5-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="703d5-110">Riservato per uso interno dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="703d5-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="703d5-111">Metodo InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="703d5-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="703d5-112">Installa l'assembly specificato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="703d5-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="703d5-113">Metodo QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="703d5-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="703d5-114">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="703d5-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="703d5-115">Metodo UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="703d5-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="703d5-116">Disinstalla l'assembly specificato dalla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="703d5-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="703d5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="703d5-117">Requirements</span></span>  
 <span data-ttu-id="703d5-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="703d5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="703d5-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="703d5-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="703d5-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="703d5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703d5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="703d5-121">See also</span></span>
- [<span data-ttu-id="703d5-122">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="703d5-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="703d5-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="703d5-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
