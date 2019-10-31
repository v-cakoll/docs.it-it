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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132327"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="c78fd-102">Struttura COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="c78fd-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="c78fd-103">Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="c78fd-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c78fd-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c78fd-105">Members</span><span class="sxs-lookup"><span data-stu-id="c78fd-105">Members</span></span>  
  
|<span data-ttu-id="c78fd-106">Member</span><span class="sxs-lookup"><span data-stu-id="c78fd-106">Member</span></span>|<span data-ttu-id="c78fd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c78fd-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="c78fd-108">`true` se Garbage Collection strutture sono valide e l'heap può essere enumerato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c78fd-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="c78fd-109">Dimensione, in byte, dei puntatori nell'architettura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c78fd-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="c78fd-110">Numero di heap Garbage Collection logici nel processo.</span><span class="sxs-lookup"><span data-stu-id="c78fd-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="c78fd-111">`TRUE` se Garbage Collection simultaneo (sfondo) è abilitato; in caso contrario, `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="c78fd-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="c78fd-112">Membro dell'enumerazione [CorDebugGCType](cordebuggctype-enumeration.md) che indica se il Garbage Collector è in esecuzione su una workstation o un server.</span><span class="sxs-lookup"><span data-stu-id="c78fd-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c78fd-113">Note</span><span class="sxs-lookup"><span data-stu-id="c78fd-113">Remarks</span></span>  
 <span data-ttu-id="c78fd-114">Un'istanza della struttura `COR_HEAPINFO` viene restituita chiamando il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c78fd-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="c78fd-115">Prima di enumerare gli oggetti nell'heap di Garbage Collection, è sempre necessario controllare il campo `areGCStructuresValid` per assicurarsi che l'heap sia in uno stato enumerabile.</span><span class="sxs-lookup"><span data-stu-id="c78fd-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="c78fd-116">Per ulteriori informazioni, vedere il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c78fd-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78fd-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c78fd-117">Requirements</span></span>  
 <span data-ttu-id="c78fd-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c78fd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c78fd-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c78fd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c78fd-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c78fd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c78fd-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78fd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78fd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c78fd-122">See also</span></span>

- [<span data-ttu-id="c78fd-123">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="c78fd-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c78fd-124">Debug</span><span class="sxs-lookup"><span data-stu-id="c78fd-124">Debugging</span></span>](index.md)
