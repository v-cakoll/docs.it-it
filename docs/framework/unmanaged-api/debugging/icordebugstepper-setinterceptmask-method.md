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
ms.openlocfilehash: 9792abb4ee38a45aae59eaf79f1f0499539bd2ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791759"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="66aed-102">Metodo ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="66aed-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="66aed-103">Imposta un valore che specifica i tipi di codice sottoposti a istruzione.</span><span class="sxs-lookup"><span data-stu-id="66aed-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66aed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66aed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66aed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66aed-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="66aed-106">in Combinazione di valori dell'enumerazione CorDebugIntercept che specifica i tipi di codice.</span><span class="sxs-lookup"><span data-stu-id="66aed-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66aed-107">Note</span><span class="sxs-lookup"><span data-stu-id="66aed-107">Remarks</span></span>  
 <span data-ttu-id="66aed-108">Se viene impostato il bit per un intercettore, il stepper verrà completato quando viene rilevato il tipo di codice di intercettazione specificato.</span><span class="sxs-lookup"><span data-stu-id="66aed-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="66aed-109">Se il bit è deselezionato, il codice di intercettazione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="66aed-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="66aed-110">Il metodo `SetInterceptMask` può avere interazioni impreviste con [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (dal punto di vista dell'utente).</span><span class="sxs-lookup"><span data-stu-id="66aed-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="66aed-111">Se, ad esempio, l'unica parte visibile (ovvero non interna) del codice di inizializzazione della classe non dispone di informazioni di mapping e non STOP_NO_MAPPING_INFO è impostato (vedere il metodo [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) e l'enumerazione CorDebugUnmappedStop), il gestore di istruzioni eseguirà il passaggio dell'inizializzazione della classe.</span><span class="sxs-lookup"><span data-stu-id="66aed-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="66aed-112">Per impostazione predefinita, verrà utilizzato solo il valore INTERCEPT_NONE dell'enumerazione `CorDebugIntercept`.</span><span class="sxs-lookup"><span data-stu-id="66aed-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66aed-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="66aed-113">Requirements</span></span>  
 <span data-ttu-id="66aed-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66aed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66aed-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66aed-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66aed-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66aed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66aed-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66aed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
