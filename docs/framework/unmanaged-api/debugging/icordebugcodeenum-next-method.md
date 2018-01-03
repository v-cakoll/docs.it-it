---
title: Metodo ICorDebugCodeEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCodeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dbc7985ebf2fff5fa0c5b524b8d6560f75318d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="10c49-102">Metodo ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="10c49-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="10c49-103">Ottiene il numero specificato di istanze di "ICorDebugCode" dell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="10c49-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10c49-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10c49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10c49-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="10c49-106">[in] Il numero di `ICorDebugCode` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="10c49-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="10c49-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugCode` oggetto.</span><span class="sxs-lookup"><span data-stu-id="10c49-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="10c49-108">[out] Un puntatore al numero di `ICorDebugCode` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="10c49-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="10c49-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="10c49-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c49-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10c49-110">Requirements</span></span>  
 <span data-ttu-id="10c49-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c49-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c49-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="10c49-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10c49-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10c49-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10c49-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c49-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10c49-115">See Also</span></span>  
    
 
