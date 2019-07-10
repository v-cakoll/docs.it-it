---
title: Metodo IHostIoCompletionManager::Bind
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d73b8b635be78472374668bbcc36541616705651
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736552"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="ac2f6-102">Metodo IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="ac2f6-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="ac2f6-103">Associa l'handle specificato per una porta di completamento i/o che è stata creata da una precedente chiamata a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="ac2f6-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac2f6-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac2f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac2f6-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="ac2f6-106">[in] La porta di completamento i/o a cui associare `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="ac2f6-107">Se il valore di `hPort` è null, `hHandle` è associata alla porta di completamento i/o predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="ac2f6-108">[in] L'handle del sistema operativo a cui associarsi `hPort`.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2f6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac2f6-109">Return Value</span></span>  
  
|<span data-ttu-id="ac2f6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac2f6-110">HRESULT</span></span>|<span data-ttu-id="ac2f6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac2f6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac2f6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac2f6-112">S_OK</span></span>|<span data-ttu-id="ac2f6-113">`Bind` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="ac2f6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac2f6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac2f6-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac2f6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac2f6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac2f6-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-117">The call timed out.</span></span>|  
|<span data-ttu-id="ac2f6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac2f6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac2f6-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac2f6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac2f6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac2f6-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac2f6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac2f6-122">E_FAIL</span></span>|<span data-ttu-id="ac2f6-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac2f6-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac2f6-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac2f6-126">Note</span><span class="sxs-lookup"><span data-stu-id="ac2f6-126">Remarks</span></span>  
 <span data-ttu-id="ac2f6-127">Una porta di completamento i/o viene creata mediante una chiamata a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="ac2f6-128">CLR chiama `Bind` per associare un handle a tale porta.</span><span class="sxs-lookup"><span data-stu-id="ac2f6-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac2f6-129">Quando viene completata una richiesta dei / o, l'host deve chiamare il [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ac2f6-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2f6-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac2f6-130">Requirements</span></span>  
 <span data-ttu-id="ac2f6-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac2f6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2f6-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac2f6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac2f6-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ac2f6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac2f6-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2f6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2f6-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac2f6-135">See also</span></span>

- [<span data-ttu-id="ac2f6-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ac2f6-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
