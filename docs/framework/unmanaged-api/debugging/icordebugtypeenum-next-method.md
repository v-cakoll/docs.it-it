---
title: Metodo ICorDebugTypeEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53acf78450e455a4f9778b1e508d79a921e20ae9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="42128-102">Metodo ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="42128-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="42128-103">Ottiene il numero di istanze di "ICorDebugType" specificate da `celt` nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="42128-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42128-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42128-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42128-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42128-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="42128-106">[in] Il numero di `ICorDebugType` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="42128-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="42128-107">[out] Matrice di puntatori, ognuno dei quali punta a un `ICorDebugType` oggetto.</span><span class="sxs-lookup"><span data-stu-id="42128-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="42128-108">[out] Puntatore al numero di `ICorDebugType` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="42128-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="42128-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="42128-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42128-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42128-110">Requirements</span></span>  
 <span data-ttu-id="42128-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42128-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42128-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="42128-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42128-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42128-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42128-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42128-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42128-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42128-115">See Also</span></span>  
 
