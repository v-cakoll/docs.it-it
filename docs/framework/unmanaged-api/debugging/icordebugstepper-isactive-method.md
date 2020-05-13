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
ms.openlocfilehash: faddf30248b58c68037635480d8977f22ad077d0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379027"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="09a89-102">Metodo ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="09a89-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="09a89-103">Ottiene un valore che indica se questo ICorDebugStepper sta attualmente eseguendo un passaggio.</span><span class="sxs-lookup"><span data-stu-id="09a89-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09a89-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09a89-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="09a89-106">out Restituisce `true` se il gestore di istruzioni sta attualmente eseguendo un passaggio; in caso contrario, restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="09a89-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a89-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="09a89-107">Remarks</span></span>  
 <span data-ttu-id="09a89-108">Qualsiasi azione Step rimane attiva fino a quando il debugger non riceve una chiamata [ICorDebugManagedCallback:: StepComplete](icordebugmanagedcallback-stepcomplete-method.md) , che disattiva automaticamente il stepper.</span><span class="sxs-lookup"><span data-stu-id="09a89-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="09a89-109">Un stepper può anche essere disattivato in modo anomalo chiamando [ICorDebugStepper::D ttiva](icordebugstepper-deactivate-method.md) prima che venga raggiunta la condizione di callback.</span><span class="sxs-lookup"><span data-stu-id="09a89-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a89-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09a89-110">Requirements</span></span>  
 <span data-ttu-id="09a89-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09a89-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a89-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09a89-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09a89-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09a89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09a89-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
