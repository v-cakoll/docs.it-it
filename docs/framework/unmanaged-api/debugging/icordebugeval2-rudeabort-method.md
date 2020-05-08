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
ms.openlocfilehash: e901c65824ee8d6949c79c7778944148c0d9eb28
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976057"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="1b125-102">Metodo ICorDebugEval2::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="1b125-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="1b125-103">Interrompe il calcolo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1b125-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b125-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b125-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b125-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1b125-105">Remarks</span></span>  
 <span data-ttu-id="1b125-106">`RudeAbort`non rilascia alcun blocco che l'analizzatore possiede, quindi lascia la sessione di debug in uno stato non sicuro.</span><span class="sxs-lookup"><span data-stu-id="1b125-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="1b125-107">Chiamare questo metodo con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="1b125-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b125-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b125-108">Requirements</span></span>  
 <span data-ttu-id="1b125-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b125-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b125-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b125-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b125-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b125-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b125-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b125-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
