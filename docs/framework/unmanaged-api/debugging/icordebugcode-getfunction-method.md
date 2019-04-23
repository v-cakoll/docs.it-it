---
title: Metodo ICorDebugCode::GetFunction
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099456"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="a9ad7-102">Metodo ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="a9ad7-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="a9ad7-103">Ottiene il "ICorDebugFunction" associato "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="a9ad7-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ad7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9ad7-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9ad7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9ad7-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="a9ad7-106">[out] Un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9ad7-107">Note</span><span class="sxs-lookup"><span data-stu-id="a9ad7-107">Remarks</span></span>  
 <span data-ttu-id="a9ad7-108">`ICorDebugCode` e `ICorDebugFunction` gestire una relazione uno a uno.</span><span class="sxs-lookup"><span data-stu-id="a9ad7-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ad7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9ad7-109">Requirements</span></span>  
 <span data-ttu-id="a9ad7-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ad7-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9ad7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9ad7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9ad7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9ad7-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ad7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ad7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9ad7-114">See also</span></span>
