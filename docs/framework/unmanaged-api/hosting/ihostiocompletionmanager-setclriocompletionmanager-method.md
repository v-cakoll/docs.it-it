---
title: Metodo IHostIoCompletionManager::SetCLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5da62d8d46b71b1f9eef677d2252ec7b21a3ae4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439560"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="324db-102">Metodo IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="324db-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="324db-103">Fornisce all'host con un puntatore a interfaccia per il [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementata da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="324db-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="324db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="324db-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="324db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="324db-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="324db-106">[in] Puntatore a interfaccia a un `ICLRIoCompletionManager` istanza fornito da CLR.</span><span class="sxs-lookup"><span data-stu-id="324db-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="324db-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="324db-107">Return Value</span></span>  
  
|<span data-ttu-id="324db-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="324db-108">HRESULT</span></span>|<span data-ttu-id="324db-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="324db-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="324db-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="324db-110">S_OK</span></span>|<span data-ttu-id="324db-111">`SetCLRIoCompletionManager` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="324db-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="324db-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="324db-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="324db-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="324db-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="324db-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="324db-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="324db-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="324db-115">The call timed out.</span></span>|  
|<span data-ttu-id="324db-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="324db-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="324db-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="324db-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="324db-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="324db-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="324db-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="324db-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="324db-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="324db-120">E_FAIL</span></span>|<span data-ttu-id="324db-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="324db-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="324db-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="324db-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="324db-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="324db-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="324db-124">Note</span><span class="sxs-lookup"><span data-stu-id="324db-124">Remarks</span></span>  
 <span data-ttu-id="324db-125">Dopo che è chiamato CLR `SetCLRIoCompletionManager`, l'host deve chiamare [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) per notificare al CLR quando una richiesta dei / o è stata completata.</span><span class="sxs-lookup"><span data-stu-id="324db-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="324db-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="324db-126">Requirements</span></span>  
 <span data-ttu-id="324db-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="324db-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="324db-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="324db-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="324db-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="324db-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="324db-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="324db-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324db-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="324db-131">See Also</span></span>  
 [<span data-ttu-id="324db-132">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="324db-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="324db-133">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="324db-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
