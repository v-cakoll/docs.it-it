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
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183391"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="be4f8-102">Metodo ICorDebugController::Stop</span><span class="sxs-lookup"><span data-stu-id="be4f8-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="be4f8-103">Esegue un arresto cooperativo in tutti i thread che eseguono il codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="be4f8-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be4f8-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be4f8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be4f8-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="be4f8-106">Non usato.</span><span class="sxs-lookup"><span data-stu-id="be4f8-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be4f8-107">Note</span><span class="sxs-lookup"><span data-stu-id="be4f8-107">Remarks</span></span>  
 `Stop` <span data-ttu-id="be4f8-108">esegue un'interruzione cooperativa in tutti i thread che esegue codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="be4f8-108">performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="be4f8-109">Durante una sessione di debug solo gestito, i thread non gestiti possono continuare a eseguire (ma verrà bloccata durante il tentativo di chiamare codice gestito).</span><span class="sxs-lookup"><span data-stu-id="be4f8-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="be4f8-110">Durante una sessione di debug di interoperabilità, i thread non gestiti verranno arrestati.</span><span class="sxs-lookup"><span data-stu-id="be4f8-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="be4f8-111">Il `dwTimeoutIgnored` valore viene attualmente ignorato e trattato come INFINITE (-1).</span><span class="sxs-lookup"><span data-stu-id="be4f8-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="be4f8-112">Se l'arresto cooperativo ha esito negativo a causa di un deadlock, tutti i thread vengono sospesi ed E_TIMEOUT viene restituito.</span><span class="sxs-lookup"><span data-stu-id="be4f8-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  `Stop` <span data-ttu-id="be4f8-113">è l'unico metodo sincrono nell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="be4f8-113">is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="be4f8-114">Quando si `Stop` restituisce S_OK, il processo è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="be4f8-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="be4f8-115">Non viene assegnato alcun callback per notificare ai listener dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="be4f8-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="be4f8-116">Il debugger deve chiamare [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per consentire la ripresa del processo.</span><span class="sxs-lookup"><span data-stu-id="be4f8-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="be4f8-117">Il debugger mantiene un contatore di arresto.</span><span class="sxs-lookup"><span data-stu-id="be4f8-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="be4f8-118">Quando il conteggio arrivasse a zero, viene ripreso il controller.</span><span class="sxs-lookup"><span data-stu-id="be4f8-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="be4f8-119">Ogni chiamata a `Stop` o ogni callback inviato viene incrementato il contatore.</span><span class="sxs-lookup"><span data-stu-id="be4f8-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="be4f8-120">Ogni chiamata a `ICorDebugController::Continue` decrementa il contatore.</span><span class="sxs-lookup"><span data-stu-id="be4f8-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4f8-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be4f8-121">Requirements</span></span>  
 <span data-ttu-id="be4f8-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be4f8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4f8-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be4f8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be4f8-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be4f8-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="be4f8-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="be4f8-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be4f8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be4f8-126">See also</span></span>
