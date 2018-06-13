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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cd0fc9f86515d63533275002301eb47f11feebb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411266"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="3bb97-102">Metodo ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="3bb97-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="3bb97-103">Esegue un'interruzione cooperativa su tutti i thread che eseguono codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="3bb97-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bb97-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bb97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bb97-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="3bb97-106">Non usato.</span><span class="sxs-lookup"><span data-stu-id="3bb97-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bb97-107">Note</span><span class="sxs-lookup"><span data-stu-id="3bb97-107">Remarks</span></span>  
 <span data-ttu-id="3bb97-108">`Stop` esegue un'interruzione cooperativa su tutti i thread che esegue codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="3bb97-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="3bb97-109">Durante una sessione di debug solo gestito, il thread non gestito è possibile continuare l'esecuzione (ma verrà bloccata durante il tentativo di chiamare codice gestito).</span><span class="sxs-lookup"><span data-stu-id="3bb97-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="3bb97-110">Durante una sessione di debug di interoperabilità, il thread non gestito verrà arrestato.</span><span class="sxs-lookup"><span data-stu-id="3bb97-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="3bb97-111">Il `dwTimeoutIgnored` valore attualmente viene ignorato e trattato come infinito (-1).</span><span class="sxs-lookup"><span data-stu-id="3bb97-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="3bb97-112">Se l'interruzione cooperativa ha esito negativo a causa di un deadlock, tutti i thread vengono sospesi e verrà restituito E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="3bb97-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bb97-113">`Stop` è l'unico metodo sincrono nell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="3bb97-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="3bb97-114">Quando `Stop` restituisce S_OK, il processo è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="3bb97-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="3bb97-115">Il callback non viene assegnato da notificare listener dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="3bb97-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="3bb97-116">Il debugger deve chiamare [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per consentire la ripresa del processo.</span><span class="sxs-lookup"><span data-stu-id="3bb97-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="3bb97-117">Il debugger gestisce un contatore di arresto.</span><span class="sxs-lookup"><span data-stu-id="3bb97-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="3bb97-118">Quando il contatore è pari a zero, il controller viene ripreso.</span><span class="sxs-lookup"><span data-stu-id="3bb97-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="3bb97-119">Ogni chiamata a `Stop` o ogni callback inviato incrementa il contatore.</span><span class="sxs-lookup"><span data-stu-id="3bb97-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="3bb97-120">Ogni chiamata a `ICorDebugController::Continue` decrementa il contatore.</span><span class="sxs-lookup"><span data-stu-id="3bb97-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb97-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3bb97-121">Requirements</span></span>  
 <span data-ttu-id="3bb97-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb97-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb97-123">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3bb97-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bb97-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3bb97-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bb97-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb97-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb97-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bb97-126">See Also</span></span>  
 
