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
ms.openlocfilehash: d4166b63e0bb0ae276c48abb961e381809cc9792
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763750"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="6930b-102">Metodo ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="6930b-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="6930b-103">Ottiene un valore che indica se questo ICorDebugStepper è in esecuzione un passaggio.</span><span class="sxs-lookup"><span data-stu-id="6930b-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6930b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6930b-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6930b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6930b-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="6930b-106">[out] Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un'istruzione; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="6930b-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6930b-107">Note</span><span class="sxs-lookup"><span data-stu-id="6930b-107">Remarks</span></span>  
 <span data-ttu-id="6930b-108">Qualsiasi azione passaggio rimane attivo finché il debugger non riceve un [StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) chiamare, che disattiva automaticamente il gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6930b-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="6930b-109">Un gestore di istruzioni può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) prima del callback di condizione viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="6930b-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6930b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6930b-110">Requirements</span></span>  
 <span data-ttu-id="6930b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6930b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6930b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6930b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6930b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6930b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6930b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6930b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
