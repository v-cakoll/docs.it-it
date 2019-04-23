---
title: Metodo IHostIoCompletionManager::CloseIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32a7c8b1c1c61eddb18ade1e77af5ea973fbaadc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107562"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="8ff1d-102">Metodo IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="8ff1d-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="8ff1d-103">Richiede che l'host di chiuda una porta che è stato aperto tramite una chiamata precedente a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="8ff1d-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ff1d-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ff1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ff1d-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="8ff1d-106">[in] Handle della porta da chiudere.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ff1d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ff1d-107">Return Value</span></span>  
  
|<span data-ttu-id="8ff1d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ff1d-108">HRESULT</span></span>|<span data-ttu-id="8ff1d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ff1d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ff1d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ff1d-110">S_OK</span></span>|<span data-ttu-id="8ff1d-111">`CloseIoCompletionPort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="8ff1d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ff1d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ff1d-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ff1d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ff1d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ff1d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ff1d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ff1d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ff1d-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ff1d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ff1d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ff1d-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ff1d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ff1d-120">E_FAIL</span></span>|<span data-ttu-id="8ff1d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ff1d-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ff1d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ff1d-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8ff1d-124">E_INVALIDARG</span></span>|<span data-ttu-id="8ff1d-125">È stato passato un handle di porta non valido.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ff1d-126">Note</span><span class="sxs-lookup"><span data-stu-id="8ff1d-126">Remarks</span></span>  
 <span data-ttu-id="8ff1d-127">`hPort` deve essere un handle a una porta che è stato creato da una precedente chiamata a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="8ff1d-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff1d-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ff1d-128">Requirements</span></span>  
 <span data-ttu-id="8ff1d-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff1d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff1d-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ff1d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ff1d-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8ff1d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ff1d-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff1d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff1d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff1d-133">See also</span></span>

- [<span data-ttu-id="8ff1d-134">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="8ff1d-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8ff1d-135">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="8ff1d-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
