---
title: Metodo ICorDebugCode::GetFunction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d05d5d7172a43ebaa04155fb42c2711eaf1ac085
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="e68b3-102">Metodo ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="e68b3-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="e68b3-103">Ottiene il "ICorDebugFunction" associato "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="e68b3-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e68b3-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e68b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e68b3-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="e68b3-106">[out] Un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="e68b3-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e68b3-107">Note</span><span class="sxs-lookup"><span data-stu-id="e68b3-107">Remarks</span></span>  
 <span data-ttu-id="e68b3-108">`ICorDebugCode`e `ICorDebugFunction` mantenere una relazione uno a uno.</span><span class="sxs-lookup"><span data-stu-id="e68b3-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e68b3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e68b3-109">Requirements</span></span>  
 <span data-ttu-id="e68b3-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e68b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e68b3-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e68b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e68b3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e68b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e68b3-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e68b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68b3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e68b3-114">See Also</span></span>  
 
