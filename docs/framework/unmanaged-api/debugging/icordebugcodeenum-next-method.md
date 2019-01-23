---
title: Metodo ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45caad20ef7d2dbe35e0381fb8cd697fc526398f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529804"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="6b5cb-102">Metodo ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6b5cb-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="6b5cb-103">Ottiene il numero di istanze di "ICorDebugCode" specificato dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="6b5cb-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b5cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b5cb-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b5cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b5cb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6b5cb-106">[in] Il numero di `ICorDebugCode` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="6b5cb-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="6b5cb-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugCode` oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b5cb-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6b5cb-108">[out] Un puntatore al numero di `ICorDebugCode` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="6b5cb-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="6b5cb-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="6b5cb-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b5cb-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b5cb-110">Requirements</span></span>  
 <span data-ttu-id="6b5cb-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b5cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b5cb-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b5cb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b5cb-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b5cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b5cb-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b5cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5cb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b5cb-115">See also</span></span>


