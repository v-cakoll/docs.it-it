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
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430583"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="38d72-102">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="38d72-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="38d72-103">Rappresenta la global assembly cache per l'utilizzo dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="38d72-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38d72-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="38d72-104">Methods</span></span>  
  
|<span data-ttu-id="38d72-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="38d72-105">Method</span></span>|<span data-ttu-id="38d72-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38d72-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38d72-107">Metodo CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="38d72-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="38d72-108">Ottiene un riferimento a un nuovo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="38d72-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="38d72-109">Metodo CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="38d72-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="38d72-110">Riservato per uso interno dalla tecnologia fusion.</span><span class="sxs-lookup"><span data-stu-id="38d72-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="38d72-111">Metodo InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="38d72-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="38d72-112">Installa l'assembly specificato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="38d72-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="38d72-113">Metodo QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="38d72-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="38d72-114">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="38d72-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="38d72-115">Metodo UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="38d72-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="38d72-116">Disinstalla l'assembly specificato dalla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="38d72-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38d72-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38d72-117">Requirements</span></span>  
 <span data-ttu-id="38d72-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d72-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d72-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="38d72-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="38d72-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d72-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d72-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d72-121">See Also</span></span>  
 [<span data-ttu-id="38d72-122">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="38d72-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="38d72-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="38d72-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
