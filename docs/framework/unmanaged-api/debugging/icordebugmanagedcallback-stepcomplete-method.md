---
title: Metodo ICorDebugManagedCallback::StepComplete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.StepComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eabc9a2730a1afdf574cee97a6f1b40bae34c7ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="8dd0a-102">Metodo ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="8dd0a-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="8dd0a-103">Notifica al debugger che un passaggio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dd0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8dd0a-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dd0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8dd0a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8dd0a-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="8dd0a-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="8dd0a-108">[in] Un puntatore a un oggetto ICorDebugStepper che rappresenta il passaggio dell'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="8dd0a-109">[in] Valore dell'enumerazione CorDebugStepReason che indica il risultato di un singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dd0a-110">Note</span><span class="sxs-lookup"><span data-stu-id="8dd0a-110">Remarks</span></span>  
 <span data-ttu-id="8dd0a-111">Il gestore di istruzioni può essere usata per continuare l'esecuzione di istruzioni se si desidera, a meno che non viene terminato il debug.</span><span class="sxs-lookup"><span data-stu-id="8dd0a-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dd0a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8dd0a-112">Requirements</span></span>  
 <span data-ttu-id="8dd0a-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dd0a-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8dd0a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dd0a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dd0a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dd0a-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dd0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd0a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dd0a-117">See Also</span></span>  
 [<span data-ttu-id="8dd0a-118">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8dd0a-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
