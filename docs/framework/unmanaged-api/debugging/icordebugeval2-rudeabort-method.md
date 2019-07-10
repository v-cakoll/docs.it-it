---
title: Metodo ICorDebugEval2::RudeAbort
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754346"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="347d6-102">Metodo ICorDebugEval2::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="347d6-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="347d6-103">Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="347d6-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="347d6-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="347d6-105">Note</span><span class="sxs-lookup"><span data-stu-id="347d6-105">Remarks</span></span>  
 <span data-ttu-id="347d6-106">`RudeAbort` non rilascia i blocchi che contiene l'analizzatore, in modo che lascia la sessione di debug in uno stato non sicuro.</span><span class="sxs-lookup"><span data-stu-id="347d6-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="347d6-107">Chiamare questo metodo con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="347d6-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="347d6-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="347d6-108">Requirements</span></span>  
 <span data-ttu-id="347d6-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="347d6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="347d6-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="347d6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="347d6-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="347d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="347d6-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="347d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
