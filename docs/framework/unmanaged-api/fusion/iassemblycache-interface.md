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
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796772"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="3e0f0-102">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="3e0f0-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="3e0f0-103">Rappresenta l'Global Assembly Cache per l'utilizzo da parte della tecnologia Fusion.</span><span class="sxs-lookup"><span data-stu-id="3e0f0-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e0f0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e0f0-104">Methods</span></span>  
  
|<span data-ttu-id="3e0f0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3e0f0-105">Method</span></span>|<span data-ttu-id="3e0f0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e0f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e0f0-107">Metodo CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="3e0f0-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="3e0f0-108">Ottiene un riferimento a un nuovo [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3e0f0-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="3e0f0-109">Metodo CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="3e0f0-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="3e0f0-110">Riservato per uso interno da parte della tecnologia Fusion.</span><span class="sxs-lookup"><span data-stu-id="3e0f0-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="3e0f0-111">Metodo InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="3e0f0-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="3e0f0-112">Installa l'assembly specificato nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="3e0f0-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="3e0f0-113">Metodo QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="3e0f0-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="3e0f0-114">Ottiene i dati richiesti sull'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="3e0f0-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="3e0f0-115">Metodo UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="3e0f0-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="3e0f0-116">Disinstalla l'assembly specificato dal Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="3e0f0-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e0f0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e0f0-117">Requirements</span></span>  
 <span data-ttu-id="3e0f0-118">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e0f0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e0f0-119">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3e0f0-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3e0f0-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e0f0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0f0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e0f0-121">See also</span></span>

- [<span data-ttu-id="3e0f0-122">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="3e0f0-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="3e0f0-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="3e0f0-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
