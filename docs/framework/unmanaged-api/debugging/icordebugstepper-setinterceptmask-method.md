---
title: Metodo ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760698"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="5c133-102">Metodo ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="5c133-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="5c133-103">Imposta un valore che specifica i tipi di codice che viene eseguita l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="5c133-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c133-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c133-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c133-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c133-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="5c133-106">[in] Una combinazione di valori dell'enumerazione CorDebugIntercept che specifica i tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="5c133-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c133-107">Note</span><span class="sxs-lookup"><span data-stu-id="5c133-107">Remarks</span></span>  
 <span data-ttu-id="5c133-108">Se il bit di un intercettore è impostato, il gestore di istruzioni verrà completata quando viene rilevato il tipo specificato di intercettazione di codice.</span><span class="sxs-lookup"><span data-stu-id="5c133-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="5c133-109">Se il bit è deselezionato, il codice di intercettazione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="5c133-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="5c133-110">Il `SetInterceptMask` metodo può avere interazioni impreviste con [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (dal punto di vista dell'utente).</span><span class="sxs-lookup"><span data-stu-id="5c133-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="5c133-111">Ad esempio, se visibile solo (vale a dire, non interno) parte del codice di inizializzazione classe non dispone di informazioni di mapping e non è impostato alcun STOP_NO_MAPPING_INFO (vedere la [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (metodo) e il Enumerazione CorDebugUnmappedStop), il salterà l'inizializzazione della classe.</span><span class="sxs-lookup"><span data-stu-id="5c133-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="5c133-112">Per impostazione predefinita, solo il valore INTERCEPT_NONE del `CorDebugIntercept` enumerazione verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5c133-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c133-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c133-113">Requirements</span></span>  
 <span data-ttu-id="5c133-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c133-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c133-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c133-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c133-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c133-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c133-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c133-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
