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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179304"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="4afa3-102">Struttura COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="4afa3-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="4afa3-103">Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="4afa3-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afa3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4afa3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4afa3-105">Members</span><span class="sxs-lookup"><span data-stu-id="4afa3-105">Members</span></span>  
  
|<span data-ttu-id="4afa3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4afa3-106">Member</span></span>|<span data-ttu-id="4afa3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4afa3-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="4afa3-108">`true`se le strutture di Garbage Collection sono valide e l'heap può essere enumerato; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="4afa3-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="4afa3-109">Dimensione, in byte, dei puntatori nell'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4afa3-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="4afa3-110">Numero di heap di Garbage Collection logici nel processo.</span><span class="sxs-lookup"><span data-stu-id="4afa3-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="4afa3-111">`TRUE`se l'operazione di Garbage Collection simultanea (in background) è abilitata; in `FALSE`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="4afa3-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="4afa3-112">Membro dell'enumerazione [CorDebugGCType](cordebuggctype-enumeration.md) che indica se il Garbage Collector è in esecuzione su una workstation o su un server.</span><span class="sxs-lookup"><span data-stu-id="4afa3-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4afa3-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4afa3-113">Remarks</span></span>  
 <span data-ttu-id="4afa3-114">Un'istanza `COR_HEAPINFO` della struttura viene restituita chiamando il [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4afa3-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="4afa3-115">Prima di enumerare gli oggetti nell'heap `areGCStructuresValid` di Garbage Collection, è necessario controllare sempre il campo per assicurarsi che l'heap sia in uno stato enumerabile.</span><span class="sxs-lookup"><span data-stu-id="4afa3-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="4afa3-116">Per altre informazioni, vedere il [metodo ICorDebugProcess5::GetGCHeapInformation.For more information, see the ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="4afa3-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4afa3-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4afa3-117">Requirements</span></span>  
 <span data-ttu-id="4afa3-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4afa3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4afa3-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4afa3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4afa3-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4afa3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4afa3-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4afa3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afa3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afa3-122">See also</span></span>

- [<span data-ttu-id="4afa3-123">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="4afa3-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4afa3-124">Debug</span><span class="sxs-lookup"><span data-stu-id="4afa3-124">Debugging</span></span>](index.md)
