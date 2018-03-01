---
title: Metodo ICorDebugController::Continue
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a96145801aa8ef6482e30e9c00b763d2501f36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="2cf5a-102">Metodo ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="2cf5a-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="2cf5a-103">Riprende l'esecuzione dei thread gestiti dopo una chiamata a [metodo Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="2cf5a-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cf5a-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cf5a-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="2cf5a-106">[in] Impostare su `true` Se continui da un evento out of band; in caso contrario, è impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cf5a-107">Note</span><span class="sxs-lookup"><span data-stu-id="2cf5a-107">Remarks</span></span>  
 <span data-ttu-id="2cf5a-108">`Continue`continua il processo dopo una chiamata al `ICorDebugController::Stop` metodo.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="2cf5a-109">Quando si esegue il debug in modalità mista, non chiamare `Continue` sul Win32 evento thread a meno che non si continui da un evento fuori banda.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="2cf5a-110">Un *evento in banda* è un evento gestito o un normale evento non gestito durante il quale il debugger supporta l'interazione con lo stato del processo gestito.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="2cf5a-111">In questo caso, il debugger riceve il [ICorDebugUnmanagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback con il relativo `fOutOfBand` parametro impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="2cf5a-112">Un *out of band evento* è un evento non gestito durante il quale è possibile interagire con lo stato del processo gestito durante il processo viene arrestato a causa dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="2cf5a-113">In questo caso, il debugger riceve il `ICorDebugUnmanagedCallback::DebugEvent` callback con il relativo `fOutOfBand` parametro impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="2cf5a-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf5a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cf5a-114">Requirements</span></span>  
 <span data-ttu-id="2cf5a-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf5a-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2cf5a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cf5a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cf5a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cf5a-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf5a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf5a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cf5a-119">See Also</span></span>  
 
