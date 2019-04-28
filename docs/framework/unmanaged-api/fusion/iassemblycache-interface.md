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
ms.openlocfilehash: 9fc5f3a3d5bc5699a596bcc648a7153190c130f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697680"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="47e48-102">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="47e48-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="47e48-103">Rappresenta la global assembly cache per l'uso con la tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="47e48-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47e48-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="47e48-104">Methods</span></span>  
  
|<span data-ttu-id="47e48-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="47e48-105">Method</span></span>|<span data-ttu-id="47e48-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47e48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47e48-107">Metodo CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="47e48-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="47e48-108">Ottiene un riferimento a una nuova [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="47e48-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="47e48-109">Metodo CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="47e48-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="47e48-110">Riservato per uso interno dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="47e48-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="47e48-111">Metodo InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="47e48-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="47e48-112">Installa l'assembly specificato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="47e48-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="47e48-113">Metodo QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="47e48-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="47e48-114">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="47e48-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="47e48-115">Metodo UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="47e48-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="47e48-116">Disinstalla l'assembly specificato dalla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="47e48-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47e48-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47e48-117">Requirements</span></span>  
 <span data-ttu-id="47e48-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47e48-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47e48-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="47e48-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="47e48-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47e48-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e48-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47e48-121">See also</span></span>

- [<span data-ttu-id="47e48-122">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="47e48-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="47e48-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="47e48-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
