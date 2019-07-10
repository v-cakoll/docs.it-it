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
ms.openlocfilehash: 10ab92c660353bea85bbd0918a25f716898ef837
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747529"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="0eb54-102">Metodo ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="0eb54-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="0eb54-103">Ottiene il "ICorDebugFunction" associato "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="0eb54-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0eb54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb54-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0eb54-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="0eb54-106">[out] Un puntatore all'indirizzo della funzione.</span><span class="sxs-lookup"><span data-stu-id="0eb54-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eb54-107">Note</span><span class="sxs-lookup"><span data-stu-id="0eb54-107">Remarks</span></span>  
 <span data-ttu-id="0eb54-108">`ICorDebugCode` e `ICorDebugFunction` gestire una relazione uno a uno.</span><span class="sxs-lookup"><span data-stu-id="0eb54-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb54-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0eb54-109">Requirements</span></span>  
 <span data-ttu-id="0eb54-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eb54-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eb54-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eb54-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eb54-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eb54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eb54-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eb54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb54-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eb54-114">See also</span></span>
