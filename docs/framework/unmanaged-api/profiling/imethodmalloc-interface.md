---
title: Interfaccia IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447557"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="20453-102">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="20453-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="20453-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span><span class="sxs-lookup"><span data-stu-id="20453-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20453-104">The `IMethodMalloc` interface is a simple memory allocator.</span><span class="sxs-lookup"><span data-stu-id="20453-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="20453-105">It allows you to allocate memory, but not to free it.</span><span class="sxs-lookup"><span data-stu-id="20453-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20453-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="20453-106">Methods</span></span>  
  
|<span data-ttu-id="20453-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="20453-107">Method</span></span>|<span data-ttu-id="20453-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20453-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20453-109">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="20453-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="20453-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span><span class="sxs-lookup"><span data-stu-id="20453-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20453-111">Note</span><span class="sxs-lookup"><span data-stu-id="20453-111">Remarks</span></span>  
 <span data-ttu-id="20453-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span><span class="sxs-lookup"><span data-stu-id="20453-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="20453-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span><span class="sxs-lookup"><span data-stu-id="20453-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20453-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20453-114">Requirements</span></span>  
 <span data-ttu-id="20453-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20453-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20453-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20453-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20453-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20453-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20453-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20453-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20453-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20453-119">See also</span></span>

- [<span data-ttu-id="20453-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="20453-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
