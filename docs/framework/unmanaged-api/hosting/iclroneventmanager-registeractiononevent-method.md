---
title: Metodo ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: e634b3876d51d461446ed3f5ae537ac1db1545bd
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703507"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="7e67c-102">Metodo ICLROnEventManager::RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="7e67c-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="7e67c-103">Registra un puntatore di callback per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="7e67c-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e67c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e67c-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e67c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e67c-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="7e67c-106">in Uno dei valori di [EClrEvent](eclrevent-enumeration.md) , che indica l'evento per il quale registrare il puntatore di callback descritto da `pAction` .</span><span class="sxs-lookup"><span data-stu-id="7e67c-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="7e67c-107">in Puntatore a un oggetto [IActionOnCLREvent](iactiononclrevent-interface.md) che viene chiamato quando viene generato l'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="7e67c-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e67c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e67c-108">Return Value</span></span>  
  
|<span data-ttu-id="7e67c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e67c-109">HRESULT</span></span>|<span data-ttu-id="7e67c-110">Description</span><span class="sxs-lookup"><span data-stu-id="7e67c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e67c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e67c-111">S_OK</span></span>|<span data-ttu-id="7e67c-112">`RegisterActionOnEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="7e67c-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7e67c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e67c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e67c-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7e67c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e67c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e67c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e67c-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7e67c-116">The call timed out.</span></span>|  
|<span data-ttu-id="7e67c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e67c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e67c-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="7e67c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e67c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e67c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e67c-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7e67c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e67c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e67c-121">E_FAIL</span></span>|<span data-ttu-id="7e67c-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7e67c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e67c-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7e67c-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e67c-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e67c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e67c-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7e67c-125">Remarks</span></span>  
 <span data-ttu-id="7e67c-126">L'host può registrare i callback per uno o entrambi i due tipi di evento descritti da `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="7e67c-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="7e67c-127">L'host ottiene l' `ICLROnEventManager` interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7e67c-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e67c-128">Gli eventi `RegisterActionOnEvent` registrati possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="7e67c-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e67c-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e67c-129">Requirements</span></span>  
 <span data-ttu-id="7e67c-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e67c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e67c-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7e67c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e67c-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7e67c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e67c-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e67c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e67c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e67c-134">See also</span></span>

- [<span data-ttu-id="7e67c-135">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="7e67c-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="7e67c-136">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="7e67c-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="7e67c-137">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7e67c-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="7e67c-138">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="7e67c-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
