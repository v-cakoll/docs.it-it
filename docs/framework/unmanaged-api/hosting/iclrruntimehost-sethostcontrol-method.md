---
title: Metodo ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 8d6a4e1ca934c748352b0c4f5120536a4dd24e0b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703965"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="b7ef2-102">Metodo ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="b7ef2-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="b7ef2-103">Imposta il puntatore a interfaccia che può essere utilizzato dal Common Language Runtime (CLR) per ottenere l'implementazione dell'host dell' [interfaccia IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef2-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7ef2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7ef2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7ef2-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="b7ef2-106">in Puntatore di interfaccia all'implementazione dell'host dell' [interfaccia IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef2-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7ef2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b7ef2-107">Return Value</span></span>  
  
|<span data-ttu-id="b7ef2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7ef2-108">HRESULT</span></span>|<span data-ttu-id="b7ef2-109">Description</span><span class="sxs-lookup"><span data-stu-id="b7ef2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7ef2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7ef2-110">S_OK</span></span>|<span data-ttu-id="b7ef2-111">`SetHostControl`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="b7ef2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7ef2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7ef2-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7ef2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7ef2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7ef2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-115">The call timed out.</span></span>|  
|<span data-ttu-id="b7ef2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7ef2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7ef2-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7ef2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7ef2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7ef2-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7ef2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7ef2-120">E_FAIL</span></span>|<span data-ttu-id="b7ef2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7ef2-122">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7ef2-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7ef2-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="b7ef2-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="b7ef2-125">CLR già inizializzato.</span><span class="sxs-lookup"><span data-stu-id="b7ef2-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ef2-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b7ef2-126">Remarks</span></span>  
 <span data-ttu-id="b7ef2-127">È necessario chiamare `SetHostControl` prima di inizializzare CLR, ovvero prima di chiamare il [metodo Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o utilizzare una qualsiasi delle [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef2-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="b7ef2-128">Si consiglia di chiamare `SetHostControl` immediatamente dopo aver chiamato la funzione [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o la [funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef2-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ef2-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7ef2-129">Requirements</span></span>  
 <span data-ttu-id="b7ef2-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ef2-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ef2-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b7ef2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7ef2-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b7ef2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7ef2-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ef2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ef2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7ef2-134">See also</span></span>

- [<span data-ttu-id="b7ef2-135">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b7ef2-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="b7ef2-136">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="b7ef2-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
