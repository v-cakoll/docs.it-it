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
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994318"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="364e6-102">Metodo ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="364e6-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="364e6-103">Fa sì che questo ICorDebugStepper passo a passo del thread e, facoltativamente, per continuare il debug passo-passo tramite le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="364e6-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="364e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="364e6-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="364e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="364e6-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="364e6-106">[in] Impostare su `true` al passaggio in una funzione che viene chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="364e6-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="364e6-107">Impostare su `false` per Esegui istruzione/routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="364e6-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="364e6-108">Note</span><span class="sxs-lookup"><span data-stu-id="364e6-108">Remarks</span></span>  
 <span data-ttu-id="364e6-109">Il passaggio viene completato quando common language runtime esegue la successiva istruzione gestita nel frame del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="364e6-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="364e6-110">Se `Step` viene chiamato su un gestore, che non si trova in codice gestito, il passaggio verrà completata quando la successiva istruzione di codice gestito viene eseguita dal thread.</span><span class="sxs-lookup"><span data-stu-id="364e6-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="364e6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="364e6-111">Requirements</span></span>  
 <span data-ttu-id="364e6-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="364e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="364e6-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="364e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="364e6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="364e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="364e6-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="364e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
