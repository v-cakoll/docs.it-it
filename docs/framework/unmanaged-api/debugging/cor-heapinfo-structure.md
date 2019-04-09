---
title: Struttura COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090355"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="ceff6-102">Struttura COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="ceff6-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="ceff6-103">Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="ceff6-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceff6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ceff6-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ceff6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ceff6-105">Members</span></span>  
  
|<span data-ttu-id="ceff6-106">Member</span><span class="sxs-lookup"><span data-stu-id="ceff6-106">Member</span></span>|<span data-ttu-id="ceff6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceff6-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` <span data-ttu-id="ceff6-108">Se le strutture di garbage collection sono valide e possono essere enumerati heap; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ceff6-108">if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="ceff6-109">Le dimensioni, in byte, dei puntatori sull'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ceff6-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="ceff6-110">Il numero di logica di garbage collection heap nel processo.</span><span class="sxs-lookup"><span data-stu-id="ceff6-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|`TRUE` <span data-ttu-id="ceff6-111">Se simultanee garbage collection (in background) è abilitata. in caso contrario, `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="ceff6-111">if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="ceff6-112">Un membro del [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumerazione che indica se il garbage collector è in esecuzione in una workstation o un server.</span><span class="sxs-lookup"><span data-stu-id="ceff6-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceff6-113">Note</span><span class="sxs-lookup"><span data-stu-id="ceff6-113">Remarks</span></span>  
 <span data-ttu-id="ceff6-114">Un'istanza di `COR_HEAPINFO` struttura viene restituita chiamando il [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ceff6-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="ceff6-115">Prima di enumerazione di oggetti nell'heap di garbage collection, è necessario verificare sempre il `areGCStructuresValid` campo per garantire che l'heap è in uno stato enumerabile.</span><span class="sxs-lookup"><span data-stu-id="ceff6-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="ceff6-116">Per altre informazioni, vedere la [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ceff6-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceff6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ceff6-117">Requirements</span></span>  
 <span data-ttu-id="ceff6-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceff6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceff6-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceff6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceff6-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceff6-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ceff6-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ceff6-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ceff6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceff6-122">See also</span></span>

- [<span data-ttu-id="ceff6-123">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="ceff6-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ceff6-124">Debug</span><span class="sxs-lookup"><span data-stu-id="ceff6-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
