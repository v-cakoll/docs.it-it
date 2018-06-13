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
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419224"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="1a34e-102">Metodo ICorDebugStepper::Step</span><span class="sxs-lookup"><span data-stu-id="1a34e-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="1a34e-103">Fa sì che ICorDebugStepper passo a passo del thread e, facoltativamente, per continuare l'esecuzione passo passo tramite le funzioni che vengono chiamate all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="1a34e-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a34e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a34e-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a34e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a34e-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="1a34e-106">[in] Impostare su `true` al passaggio a una funzione che viene chiamata all'interno del thread.</span><span class="sxs-lookup"><span data-stu-id="1a34e-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="1a34e-107">Impostare su `false` per Esegui istruzione/routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="1a34e-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a34e-108">Note</span><span class="sxs-lookup"><span data-stu-id="1a34e-108">Remarks</span></span>  
 <span data-ttu-id="1a34e-109">Il passaggio viene completato quando common language runtime esegue la successiva istruzione gestita nel frame del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1a34e-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="1a34e-110">Se `Step` viene chiamato su un gestore, che non è in codice gestito, il passaggio verrà completata quando la successiva istruzione di codice gestito viene eseguita dal thread.</span><span class="sxs-lookup"><span data-stu-id="1a34e-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a34e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a34e-111">Requirements</span></span>  
 <span data-ttu-id="1a34e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a34e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a34e-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1a34e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a34e-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1a34e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a34e-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a34e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
