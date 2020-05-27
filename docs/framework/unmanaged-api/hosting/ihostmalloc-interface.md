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
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804609"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="8a08c-102">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="8a08c-102">IHostMalloc Interface</span></span>
<span data-ttu-id="8a08c-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di richiedere allocazioni con granularità fine dall'heap tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="8a08c-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a08c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8a08c-104">Methods</span></span>  
  
|<span data-ttu-id="8a08c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8a08c-105">Method</span></span>|<span data-ttu-id="8a08c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a08c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a08c-107">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="8a08c-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="8a08c-108">Richiede che l'host allochi la quantità di memoria richiesta dall'heap.</span><span class="sxs-lookup"><span data-stu-id="8a08c-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="8a08c-109">Metodo DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="8a08c-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="8a08c-110">Richiede che l'host allochi la quantità di memoria richiesta dall'heap e tenga traccia anche della posizione in cui è stata allocata la memoria.</span><span class="sxs-lookup"><span data-stu-id="8a08c-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="8a08c-111">Metodo Free</span><span class="sxs-lookup"><span data-stu-id="8a08c-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="8a08c-112">Libera la memoria allocata tramite il `Alloc` metodo.</span><span class="sxs-lookup"><span data-stu-id="8a08c-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a08c-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8a08c-113">Remarks</span></span>  
 <span data-ttu-id="8a08c-114">CLR ottiene un puntatore a interfaccia a un' `IHostMalloc` istanza di chiamando il metodo [IHostMemoryManager:: CreateMAlloc](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a08c-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a08c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a08c-115">Requirements</span></span>  
 <span data-ttu-id="8a08c-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a08c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a08c-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a08c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a08c-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a08c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a08c-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a08c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a08c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a08c-120">See also</span></span>

- [<span data-ttu-id="8a08c-121">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="8a08c-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="8a08c-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8a08c-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
