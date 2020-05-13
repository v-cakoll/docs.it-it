---
title: Metodo ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: c9999961ec20a31cf82d5ad60104bcdd04c340d1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210176"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="4a4a1-102">Metodo ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4a4a1-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="4a4a1-103">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sulle aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="4a4a1-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a4a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a4a1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a4a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a4a1-105">Parameters</span></span>  
 <span data-ttu-id="4a4a1-106">celt</span><span class="sxs-lookup"><span data-stu-id="4a4a1-106">celt</span></span>  
 <span data-ttu-id="4a4a1-107">in Numero di segmenti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="4a4a1-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="4a4a1-108">segmenti</span><span class="sxs-lookup"><span data-stu-id="4a4a1-108">segments</span></span>  
 <span data-ttu-id="4a4a1-109">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="4a4a1-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="4a4a1-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="4a4a1-110">pceltFetched</span></span>  
 <span data-ttu-id="4a4a1-111">out Puntatore al numero di oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) effettivamente restituiti in `segments` .</span><span class="sxs-lookup"><span data-stu-id="4a4a1-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="4a4a1-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="4a4a1-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a4a1-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4a4a1-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a4a1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a4a1-114">Requirements</span></span>  
 <span data-ttu-id="4a4a1-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a4a1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a4a1-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a4a1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a4a1-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a4a1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a4a1-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a4a1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4a1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a4a1-119">See also</span></span>

- [<span data-ttu-id="4a4a1-120">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="4a4a1-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="4a4a1-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a4a1-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
