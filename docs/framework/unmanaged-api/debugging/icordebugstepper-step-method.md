---
title: Metodo ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d0f601c4b454b55edc5fa25eb2ee33d491009b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760575"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="f1100-102">Metodo ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="f1100-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="f1100-103">Fa sì che questo ICorDebugStepper passo a passo del thread e, facoltativamente, per continuare il debug passo-passo tramite le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="f1100-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1100-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1100-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1100-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1100-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="f1100-106">[in] Impostare su `true` al passaggio in una funzione che viene chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="f1100-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="f1100-107">Impostare su `false` per Esegui istruzione/routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="f1100-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1100-108">Note</span><span class="sxs-lookup"><span data-stu-id="f1100-108">Remarks</span></span>  
 <span data-ttu-id="f1100-109">Il passaggio viene completato quando common language runtime esegue la successiva istruzione gestita nel frame del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f1100-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="f1100-110">Se `Step` viene chiamato su un gestore, che non si trova in codice gestito, il passaggio verrà completata quando la successiva istruzione di codice gestito viene eseguita dal thread.</span><span class="sxs-lookup"><span data-stu-id="f1100-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1100-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1100-111">Requirements</span></span>  
 <span data-ttu-id="f1100-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1100-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1100-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1100-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1100-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1100-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1100-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1100-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
