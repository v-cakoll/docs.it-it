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
ms.openlocfilehash: e044b1a2ad777868e33cd64bc8d09a9b76d547aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130662"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="b4ec9-102">Metodo ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="b4ec9-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="b4ec9-103">Notifica al debugger il completamento di un passaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ec9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4ec9-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ec9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4ec9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b4ec9-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b4ec9-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="b4ec9-108">in Puntatore a un oggetto ICorDebugStepper che rappresenta il passaggio nell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="b4ec9-109">in Valore dell'enumerazione CorDebugStepReason che indica il risultato di un singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4ec9-110">Note</span><span class="sxs-lookup"><span data-stu-id="b4ec9-110">Remarks</span></span>  
 <span data-ttu-id="b4ec9-111">Il gestore di debug può essere usato per continuare l'esecuzione, se necessario, a meno che il debug non venga terminato.</span><span class="sxs-lookup"><span data-stu-id="b4ec9-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ec9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4ec9-112">Requirements</span></span>  
 <span data-ttu-id="b4ec9-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ec9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ec9-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4ec9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4ec9-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4ec9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4ec9-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ec9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ec9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4ec9-117">See also</span></span>

- [<span data-ttu-id="b4ec9-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b4ec9-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
