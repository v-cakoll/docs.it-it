---
title: Metodo ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd784cb3322423e9309e8a5632822831b4e44cdf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184795"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="476fe-102">Metodo ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="476fe-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="476fe-103">Notifica al debugger che è stato completato un passaggio.</span><span class="sxs-lookup"><span data-stu-id="476fe-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="476fe-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="476fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="476fe-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="476fe-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="476fe-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="476fe-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="476fe-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="476fe-108">[in] Un puntatore a un oggetto ICorDebugStepper che rappresenta il passaggio per l'esecuzione di codice.</span><span class="sxs-lookup"><span data-stu-id="476fe-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="476fe-109">[in] Valore dell'enumerazione CorDebugStepReason che indica il risultato di un singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="476fe-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="476fe-110">Note</span><span class="sxs-lookup"><span data-stu-id="476fe-110">Remarks</span></span>  
 <span data-ttu-id="476fe-111">Il gestore di istruzioni consente di continuare l'esecuzione di istruzioni se si desidera, a meno che il debug viene terminato.</span><span class="sxs-lookup"><span data-stu-id="476fe-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="476fe-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="476fe-112">Requirements</span></span>  
 <span data-ttu-id="476fe-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="476fe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="476fe-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="476fe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="476fe-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="476fe-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="476fe-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="476fe-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="476fe-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="476fe-117">See also</span></span>

- [<span data-ttu-id="476fe-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="476fe-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
