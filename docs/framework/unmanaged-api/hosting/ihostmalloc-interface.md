---
title: Interfaccia IHostMalloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136411"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="34b82-102">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="34b82-102">IHostMalloc Interface</span></span>
<span data-ttu-id="34b82-103">Fornisce metodi che consentono di common language runtime (CLR) per richiedere granulari per le allocazioni dall'heap tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="34b82-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34b82-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="34b82-104">Methods</span></span>  
  
|<span data-ttu-id="34b82-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="34b82-105">Method</span></span>|<span data-ttu-id="34b82-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34b82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34b82-107">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="34b82-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="34b82-108">Richieste all'host di allocare la quantità di memoria richiesta dall'heap.</span><span class="sxs-lookup"><span data-stu-id="34b82-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="34b82-109">Metodo DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="34b82-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="34b82-110">Richiede che l'host di alloca la quantità di memoria richiesta dall'heap e tenere traccia della posizione di allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="34b82-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="34b82-111">Metodo Free</span><span class="sxs-lookup"><span data-stu-id="34b82-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="34b82-112">Libera la memoria allocata tramite la `Alloc` (metodo).</span><span class="sxs-lookup"><span data-stu-id="34b82-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34b82-113">Note</span><span class="sxs-lookup"><span data-stu-id="34b82-113">Remarks</span></span>  
 <span data-ttu-id="34b82-114">Common Language Runtime Ottiene un puntatore a interfaccia a un `IHostMalloc` istanza chiamando il [CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="34b82-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b82-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34b82-115">Requirements</span></span>  
 <span data-ttu-id="34b82-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34b82-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b82-117">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34b82-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34b82-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="34b82-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="34b82-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="34b82-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34b82-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34b82-120">See also</span></span>

- [<span data-ttu-id="34b82-121">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="34b82-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="34b82-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="34b82-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
