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
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136769"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="e76db-102">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="e76db-102">IHostMalloc Interface</span></span>
<span data-ttu-id="e76db-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di richiedere allocazioni con granularità fine dall'heap tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="e76db-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e76db-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e76db-104">Methods</span></span>  
  
|<span data-ttu-id="e76db-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e76db-105">Method</span></span>|<span data-ttu-id="e76db-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e76db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e76db-107">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="e76db-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="e76db-108">Richiede che l'host allochi la quantità di memoria richiesta dall'heap.</span><span class="sxs-lookup"><span data-stu-id="e76db-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="e76db-109">Metodo DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="e76db-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="e76db-110">Richiede che l'host allochi la quantità di memoria richiesta dall'heap e tenga traccia anche della posizione in cui è stata allocata la memoria.</span><span class="sxs-lookup"><span data-stu-id="e76db-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="e76db-111">Metodo Free</span><span class="sxs-lookup"><span data-stu-id="e76db-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="e76db-112">Libera la memoria allocata tramite il metodo `Alloc`.</span><span class="sxs-lookup"><span data-stu-id="e76db-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e76db-113">Note</span><span class="sxs-lookup"><span data-stu-id="e76db-113">Remarks</span></span>  
 <span data-ttu-id="e76db-114">CLR ottiene un puntatore a interfaccia a un'istanza di `IHostMalloc` chiamando il metodo [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e76db-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e76db-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e76db-115">Requirements</span></span>  
 <span data-ttu-id="e76db-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e76db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e76db-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e76db-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e76db-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e76db-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e76db-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e76db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76db-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e76db-120">See also</span></span>

- [<span data-ttu-id="e76db-121">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="e76db-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e76db-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e76db-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
