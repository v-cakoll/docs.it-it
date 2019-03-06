---
title: Metodo ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f448a0383d3ad121cbddb59e13acef46a336261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485733"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="4cb81-102">Metodo ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="4cb81-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="4cb81-103">Riprende l'esecuzione dei thread gestiti dopo una chiamata a [metodo Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="4cb81-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cb81-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb81-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cb81-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="4cb81-106">[in] Impostare su `true` andare a un evento di out-of-band; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="4cb81-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb81-107">Note</span><span class="sxs-lookup"><span data-stu-id="4cb81-107">Remarks</span></span>  
 <span data-ttu-id="4cb81-108">`Continue` continua il processo dopo una chiamata al `ICorDebugController::Stop` (metodo).</span><span class="sxs-lookup"><span data-stu-id="4cb81-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="4cb81-109">Quando si esegue il debug in modalità mista, non chiamare `Continue` in Win32 evento thread a meno che non si continui da un evento di out-of-band.</span><span class="sxs-lookup"><span data-stu-id="4cb81-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="4cb81-110">Un' *eventi in banda* è un evento gestito o un normale evento non gestito durante il quale il debugger supporta l'interazione con la gestione degli Stati del processo.</span><span class="sxs-lookup"><span data-stu-id="4cb81-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="4cb81-111">In questo caso, il debugger riceve la [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback con relativo `fOutOfBand` parametro impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="4cb81-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="4cb81-112">Un' *evento out-of-band* è un evento non gestito durante il quale è possibile l'interazione con la gestione degli Stati del processo durante il processo viene arrestato a causa di un evento.</span><span class="sxs-lookup"><span data-stu-id="4cb81-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="4cb81-113">In questo caso, il debugger riceve la `ICorDebugUnmanagedCallback::DebugEvent` callback con relativo `fOutOfBand` parametro impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="4cb81-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb81-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cb81-114">Requirements</span></span>  
 <span data-ttu-id="4cb81-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb81-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb81-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cb81-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cb81-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb81-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb81-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb81-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb81-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cb81-119">See also</span></span>

