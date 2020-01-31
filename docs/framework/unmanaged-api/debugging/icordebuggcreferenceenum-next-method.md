---
title: Metodo ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: 3a8e967a3ecc452ebda08872d8bcd9e9d08c766f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777698"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="b2eda-102">Metodo ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b2eda-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="b2eda-103">Ottiene il numero specificato di istanze di [COR_GC_REFERENCE](cor-gc-reference-structure.md) che contengono informazioni sugli oggetti che verranno sottoposti a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2eda-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2eda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2eda-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2eda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2eda-105">Parameters</span></span>  
 <span data-ttu-id="b2eda-106">celt</span><span class="sxs-lookup"><span data-stu-id="b2eda-106">celt</span></span>  
 <span data-ttu-id="b2eda-107">in Numero di radici da recuperare.</span><span class="sxs-lookup"><span data-stu-id="b2eda-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="b2eda-108">radici</span><span class="sxs-lookup"><span data-stu-id="b2eda-108">roots</span></span>  
 <span data-ttu-id="b2eda-109">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_GC_REFERENCE](cor-gc-reference-structure.md) che rappresenta la radice di un oggetto da sottoporre a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2eda-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="b2eda-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b2eda-110">pceltFetched</span></span>  
 <span data-ttu-id="b2eda-111">out Puntatore al numero di oggetti di [COR_GC_REFERENCE](cor-gc-reference-structure.md) restituiti effettivamente nella `roots`.</span><span class="sxs-lookup"><span data-stu-id="b2eda-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="b2eda-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="b2eda-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2eda-113">Note</span><span class="sxs-lookup"><span data-stu-id="b2eda-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2eda-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b2eda-114">Requirements</span></span>  
 <span data-ttu-id="b2eda-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2eda-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2eda-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2eda-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2eda-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2eda-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2eda-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2eda-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2eda-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2eda-119">See also</span></span>

- [<span data-ttu-id="b2eda-120">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b2eda-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="b2eda-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b2eda-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
