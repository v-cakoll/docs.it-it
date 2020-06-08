---
title: Metodo ICLROnEventManager::UnregisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: a3018d8477d5abd7d03ad8675503624d2e44e8f4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504134"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="e2c65-102">Metodo ICLROnEventManager::UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="e2c65-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="e2c65-103">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="e2c65-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2c65-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2c65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2c65-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="e2c65-106">in Uno dei valori di [EClrEvent](eclrevent-enumeration.md) , che indica l'evento per il quale annullare la registrazione del puntatore di callback descritto da `pAction` .</span><span class="sxs-lookup"><span data-stu-id="e2c65-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="e2c65-107">in Puntatore a un oggetto [IActionOnCLREvent](iactiononclrevent-interface.md) passato come parametro al metodo [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e2c65-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2c65-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2c65-108">Return Value</span></span>  
  
|<span data-ttu-id="e2c65-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2c65-109">HRESULT</span></span>|<span data-ttu-id="e2c65-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2c65-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2c65-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2c65-111">S_OK</span></span>|<span data-ttu-id="e2c65-112">`UnregisterActionOnEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e2c65-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="e2c65-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2c65-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2c65-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2c65-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2c65-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2c65-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2c65-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e2c65-116">The call timed out.</span></span>|  
|<span data-ttu-id="e2c65-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2c65-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2c65-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e2c65-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2c65-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2c65-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2c65-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e2c65-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2c65-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2c65-121">E_FAIL</span></span>|<span data-ttu-id="e2c65-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e2c65-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2c65-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e2c65-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2c65-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2c65-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2c65-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2c65-125">Requirements</span></span>  
 <span data-ttu-id="e2c65-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2c65-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2c65-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2c65-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2c65-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2c65-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2c65-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2c65-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c65-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2c65-130">See also</span></span>

- [<span data-ttu-id="e2c65-131">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="e2c65-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="e2c65-132">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="e2c65-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="e2c65-133">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e2c65-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e2c65-134">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="e2c65-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
