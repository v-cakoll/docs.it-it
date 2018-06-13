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
ms.openlocfilehash: 0aabff090634f1ecdeec5636336ad1fb77b8b81c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412578"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="9599c-102">Metodo ICorDebugEval2::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="9599c-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="9599c-103">Interrompe il calcolo da questo `ICorDebugEval2` attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9599c-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9599c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9599c-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9599c-105">Note</span><span class="sxs-lookup"><span data-stu-id="9599c-105">Remarks</span></span>  
 <span data-ttu-id="9599c-106">`RudeAbort` non rilascia eventuali blocchi che contiene l'analizzatore, pertanto lascia la sessione di debug in uno stato non sicuro.</span><span class="sxs-lookup"><span data-stu-id="9599c-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="9599c-107">Chiamare questo metodo con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="9599c-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9599c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9599c-108">Requirements</span></span>  
 <span data-ttu-id="9599c-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9599c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9599c-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9599c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9599c-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9599c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9599c-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9599c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
