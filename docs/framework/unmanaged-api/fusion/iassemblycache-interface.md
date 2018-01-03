---
title: Interfaccia IAssemblyCache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache
helpviewer_keywords: IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21ebc29a6c442625f7a532f7b1e6a47e7dc4cb69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="4ba03-102">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="4ba03-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="4ba03-103">Rappresenta la global assembly cache per l'utilizzo dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="4ba03-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ba03-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4ba03-104">Methods</span></span>  
  
|<span data-ttu-id="4ba03-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4ba03-105">Method</span></span>|<span data-ttu-id="4ba03-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ba03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ba03-107">Metodo CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="4ba03-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="4ba03-108">Ottiene un riferimento a un nuovo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4ba03-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="4ba03-109">Metodo CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="4ba03-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="4ba03-110">Riservato per uso interno dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="4ba03-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="4ba03-111">Metodo InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="4ba03-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="4ba03-112">Installa l'assembly specificato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="4ba03-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="4ba03-113">Metodo QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="4ba03-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="4ba03-114">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="4ba03-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="4ba03-115">Metodo UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="4ba03-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="4ba03-116">Disinstalla l'assembly specificato dalla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="4ba03-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ba03-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ba03-117">Requirements</span></span>  
 <span data-ttu-id="4ba03-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ba03-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba03-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4ba03-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4ba03-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba03-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba03-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ba03-121">See Also</span></span>  
 [<span data-ttu-id="4ba03-122">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="4ba03-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="4ba03-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="4ba03-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
