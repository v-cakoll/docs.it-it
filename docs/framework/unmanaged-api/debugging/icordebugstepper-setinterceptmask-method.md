---
title: Metodo ICorDebugStepper::SetInterceptMask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ef03b63c4af79c01ba9962fcc6f106b3141b576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="bd04a-102">Metodo ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="bd04a-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="bd04a-103">Imposta un valore che specifica i tipi di codice che viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="bd04a-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd04a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd04a-104">Syntax</span></span>  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd04a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd04a-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="bd04a-106">[in] Una combinazione dei valori dell'enumerazione CorDebugIntercept che specifica i tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="bd04a-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd04a-107">Note</span><span class="sxs-lookup"><span data-stu-id="bd04a-107">Remarks</span></span>  
 <span data-ttu-id="bd04a-108">Se il bit di un intercettore è impostato, il gestore di istruzioni verrà completata quando viene rilevato il tipo specificato di intercettazione di codice.</span><span class="sxs-lookup"><span data-stu-id="bd04a-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="bd04a-109">Se il bit è deselezionato, il codice di intercettazione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="bd04a-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="bd04a-110">Il `SetInterceptMask` metodo potrebbe avere con [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (dal punto di vista dell'utente).</span><span class="sxs-lookup"><span data-stu-id="bd04a-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="bd04a-111">Ad esempio, se visibile solo (vale a dire non interna) parte del codice di inizializzazione classe manca le informazioni di mapping e STOP_NO_MAPPING_INFO non è impostato (vedere il [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (metodo) e Enumerazione CorDebugUnmappedStop), il salterà l'inizializzazione della classe.</span><span class="sxs-lookup"><span data-stu-id="bd04a-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="bd04a-112">Per impostazione predefinita, solo il valore INTERCEPT_NONE il `CorDebugIntercept` verrà utilizzata l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd04a-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd04a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd04a-113">Requirements</span></span>  
 <span data-ttu-id="bd04a-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd04a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd04a-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bd04a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd04a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd04a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd04a-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd04a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
