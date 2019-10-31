---
title: Metodo ICorDebugStepper::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137568"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="ef3fe-102">Metodo ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="ef3fe-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="ef3fe-103">Ottiene un valore che indica se questo ICorDebugStepper sta attualmente eseguendo un passaggio.</span><span class="sxs-lookup"><span data-stu-id="ef3fe-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef3fe-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef3fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef3fe-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="ef3fe-106">out Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un passaggio; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="ef3fe-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef3fe-107">Note</span><span class="sxs-lookup"><span data-stu-id="ef3fe-107">Remarks</span></span>  
 <span data-ttu-id="ef3fe-108">Qualsiasi azione Step rimane attiva fino a quando il debugger non riceve una chiamata [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) , che disattiva automaticamente il stepper.</span><span class="sxs-lookup"><span data-stu-id="ef3fe-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="ef3fe-109">Un stepper può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper::D ttiva](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) prima che venga raggiunta la condizione di callback.</span><span class="sxs-lookup"><span data-stu-id="ef3fe-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3fe-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef3fe-110">Requirements</span></span>  
 <span data-ttu-id="ef3fe-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef3fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3fe-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef3fe-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef3fe-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef3fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef3fe-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
