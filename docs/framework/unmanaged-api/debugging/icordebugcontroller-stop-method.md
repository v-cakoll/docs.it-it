---
title: Metodo ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: c8c6b40f7a9c63a577140209eed65436040addcb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125382"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="8f49e-102">Metodo ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="8f49e-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="8f49e-103">Esegue un arresto cooperativo su tutti i thread che eseguono codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="8f49e-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f49e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f49e-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f49e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f49e-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="8f49e-106">Non usato.</span><span class="sxs-lookup"><span data-stu-id="8f49e-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f49e-107">Note</span><span class="sxs-lookup"><span data-stu-id="8f49e-107">Remarks</span></span>  
 <span data-ttu-id="8f49e-108">`Stop` esegue un arresto cooperativo su tutti i thread che eseguono codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="8f49e-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="8f49e-109">Durante una sessione di debug solo gestita, i thread non gestiti possono continuare a essere eseguiti (ma verranno bloccati quando si tenta di chiamare il codice gestito).</span><span class="sxs-lookup"><span data-stu-id="8f49e-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="8f49e-110">Durante una sessione di debug di interoperabilità, verranno arrestati anche i thread non gestiti.</span><span class="sxs-lookup"><span data-stu-id="8f49e-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="8f49e-111">Il valore `dwTimeoutIgnored` è attualmente ignorato e trattato come infinito (-1).</span><span class="sxs-lookup"><span data-stu-id="8f49e-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="8f49e-112">Se l'arresto cooperativo non riesce a causa di un deadlock, tutti i thread vengono sospesi e viene restituito E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="8f49e-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f49e-113">`Stop` è l'unico metodo sincrono nell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="8f49e-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="8f49e-114">Quando `Stop` restituisce S_OK, il processo viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="8f49e-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="8f49e-115">Non viene specificato alcun callback per notificare ai listener l'arresto.</span><span class="sxs-lookup"><span data-stu-id="8f49e-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="8f49e-116">Il debugger deve chiamare [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per consentire la ripresa del processo.</span><span class="sxs-lookup"><span data-stu-id="8f49e-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="8f49e-117">Il debugger mantiene un contatore di interruzioni.</span><span class="sxs-lookup"><span data-stu-id="8f49e-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="8f49e-118">Quando il contatore va a zero, il controller viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="8f49e-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="8f49e-119">Ogni chiamata a `Stop` o a ogni callback inviato incrementa il contatore.</span><span class="sxs-lookup"><span data-stu-id="8f49e-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="8f49e-120">Ogni chiamata a `ICorDebugController::Continue` decrementa il contatore.</span><span class="sxs-lookup"><span data-stu-id="8f49e-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f49e-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f49e-121">Requirements</span></span>  
 <span data-ttu-id="8f49e-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f49e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f49e-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f49e-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f49e-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f49e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f49e-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f49e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f49e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f49e-126">See also</span></span>
