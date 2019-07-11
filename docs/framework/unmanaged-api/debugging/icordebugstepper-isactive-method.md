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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dde27f74ac59d033b6e25fba1dbb8e52c4b91af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760683"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="7bdc0-102">Metodo ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="7bdc0-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="7bdc0-103">Ottiene un valore che indica se questo ICorDebugStepper è in esecuzione un passaggio.</span><span class="sxs-lookup"><span data-stu-id="7bdc0-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bdc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bdc0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bdc0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7bdc0-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="7bdc0-106">[out] Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un'istruzione; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="7bdc0-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bdc0-107">Note</span><span class="sxs-lookup"><span data-stu-id="7bdc0-107">Remarks</span></span>  
 <span data-ttu-id="7bdc0-108">Qualsiasi azione passaggio rimane attivo finché il debugger non riceve un [StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) chiamare, che disattiva automaticamente il gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="7bdc0-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="7bdc0-109">Un gestore di istruzioni può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) prima del callback di condizione viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="7bdc0-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bdc0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bdc0-110">Requirements</span></span>  
 <span data-ttu-id="7bdc0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bdc0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bdc0-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bdc0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bdc0-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bdc0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bdc0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bdc0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
