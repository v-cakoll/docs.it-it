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
ms.openlocfilehash: 62e2be44165472e2fbf368f61b865d39a5e9fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395462"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="71432-102">Metodo ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="71432-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="71432-103">Riprende l'esecuzione di thread gestiti dopo una chiamata al [metodo Stop](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="71432-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="71432-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71432-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="71432-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71432-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="71432-106">in Impostare su `true` se si continua da un evento fuori banda; in caso contrario, impostare su `false`.</span><span class="sxs-lookup"><span data-stu-id="71432-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="71432-107">Note</span><span class="sxs-lookup"><span data-stu-id="71432-107">Remarks</span></span>

<span data-ttu-id="71432-108">`Continue` continua il processo dopo una chiamata al metodo `ICorDebugController::Stop`.</span><span class="sxs-lookup"><span data-stu-id="71432-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="71432-109">Quando si esegue il debug in modalità mista, non chiamare `Continue` sul thread di evento Win32 a meno che non si continui da un evento fuori banda.</span><span class="sxs-lookup"><span data-stu-id="71432-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="71432-110">Un *evento in banda* può essere un evento gestito o un evento non gestito normale durante il quale il debugger supporta l'interazione con lo stato gestito del processo.</span><span class="sxs-lookup"><span data-stu-id="71432-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="71432-111">In questo caso, il debugger riceve il callback [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) con il relativo parametro `fOutOfBand` impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="71432-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="71432-112">Un *evento fuori banda* è un evento non gestito durante il quale l'interazione con lo stato gestito del processo è Impossibile quando il processo viene interrotto a causa dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71432-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="71432-113">In questo caso, il debugger riceve il callback `ICorDebugUnmanagedCallback::DebugEvent` con il relativo parametro `fOutOfBand` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="71432-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="71432-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71432-114">Requirements</span></span>

<span data-ttu-id="71432-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71432-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="71432-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71432-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="71432-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71432-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="71432-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71432-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
