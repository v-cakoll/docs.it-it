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
ms.openlocfilehash: 39d2fd0163b0e61295187461d5dbdf5742450306
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379511"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="835cb-102">Metodo ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="835cb-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="835cb-103">Fa in modo che questo ICorDebugStepper in un unico passaggio attraverso il thread contenitore e, facoltativamente, per continuare a eseguire l'istruzione singola con le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="835cb-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="835cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="835cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="835cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="835cb-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="835cb-106">in Impostare su `true` per eseguire un'istruzione in una funzione chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="835cb-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="835cb-107">Impostare su `false` per eseguire l'istruzione/routine della funzione.</span><span class="sxs-lookup"><span data-stu-id="835cb-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="835cb-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="835cb-108">Remarks</span></span>  
 <span data-ttu-id="835cb-109">Il passaggio viene completato quando il Common Language Runtime esegue l'istruzione gestita successiva nel frame di questo stepper.</span><span class="sxs-lookup"><span data-stu-id="835cb-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="835cb-110">Se `Step` viene chiamato su un stepper, che non si trova nel codice gestito, il passaggio verrà completato quando l'istruzione del codice gestito successiva viene eseguita dal thread.</span><span class="sxs-lookup"><span data-stu-id="835cb-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="835cb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="835cb-111">Requirements</span></span>  
 <span data-ttu-id="835cb-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="835cb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="835cb-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="835cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="835cb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="835cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="835cb-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="835cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
