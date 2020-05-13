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
ms.openlocfilehash: 89b010706222ad44bccabd94191c42a888584944
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212659"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="032d4-102">Metodo ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="032d4-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="032d4-103">Notifica al debugger il completamento di un passaggio.</span><span class="sxs-lookup"><span data-stu-id="032d4-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="032d4-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="032d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="032d4-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="032d4-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="032d4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="032d4-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato completato il passaggio.</span><span class="sxs-lookup"><span data-stu-id="032d4-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="032d4-108">in Puntatore a un oggetto ICorDebugStepper che rappresenta il passaggio nell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="032d4-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="032d4-109">in Valore dell'enumerazione CorDebugStepReason che indica il risultato di un singolo passaggio.</span><span class="sxs-lookup"><span data-stu-id="032d4-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="032d4-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="032d4-110">Remarks</span></span>  
 <span data-ttu-id="032d4-111">Il gestore di debug può essere usato per continuare l'esecuzione, se necessario, a meno che il debug non venga terminato.</span><span class="sxs-lookup"><span data-stu-id="032d4-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="032d4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="032d4-112">Requirements</span></span>  
 <span data-ttu-id="032d4-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="032d4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032d4-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="032d4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="032d4-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="032d4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="032d4-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032d4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="032d4-117">See also</span></span>

- [<span data-ttu-id="032d4-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="032d4-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
