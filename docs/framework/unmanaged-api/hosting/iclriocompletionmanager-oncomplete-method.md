---
title: Metodo ICLRIoCompletionManager::OnComplete
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141016"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="89e3d-102">Metodo ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="89e3d-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="89e3d-103">Notifica al Common Language Runtime (CLR) lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89e3d-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e3d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89e3d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e3d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89e3d-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="89e3d-106">in Valore HRESULT che indica lo stato dell'operazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="89e3d-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="89e3d-107">S_OK indica che l'operazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="89e3d-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="89e3d-108">HOST_E_INTERRUPTED indica che la chiamata è stata interrotta prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="89e3d-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="89e3d-109">E_FAIL indica che si è verificato un errore irreversibile sconosciuto, irreversibile.</span><span class="sxs-lookup"><span data-stu-id="89e3d-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="89e3d-110">in Numero di byte trasferiti durante l'elaborazione della richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="89e3d-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="89e3d-111">in Puntatore alla struttura `OVERLAPPED` passata alla chiamata al metodo `IHostIoCompletionManager::Bind`.</span><span class="sxs-lookup"><span data-stu-id="89e3d-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89e3d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="89e3d-112">Return Value</span></span>  
  
|<span data-ttu-id="89e3d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89e3d-113">HRESULT</span></span>|<span data-ttu-id="89e3d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89e3d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89e3d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="89e3d-115">S_OK</span></span>|<span data-ttu-id="89e3d-116">`OnComplete` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="89e3d-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="89e3d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89e3d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89e3d-118">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="89e3d-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89e3d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89e3d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89e3d-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="89e3d-120">The call timed out.</span></span>|  
|<span data-ttu-id="89e3d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89e3d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89e3d-122">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="89e3d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89e3d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89e3d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89e3d-124">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="89e3d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89e3d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89e3d-125">E_FAIL</span></span>|<span data-ttu-id="89e3d-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="89e3d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89e3d-127">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="89e3d-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89e3d-128">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89e3d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89e3d-129">Note</span><span class="sxs-lookup"><span data-stu-id="89e3d-129">Remarks</span></span>  
 <span data-ttu-id="89e3d-130">Se l'host implementa un'astrazione di completamento I/O, CLR esegue le richieste I/O attraverso l'host usando i metodi di [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="89e3d-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="89e3d-131">L'host chiama quindi il metodo `OnComplete` per notificare al runtime il risultato di tali richieste.</span><span class="sxs-lookup"><span data-stu-id="89e3d-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e3d-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89e3d-132">Requirements</span></span>  
 <span data-ttu-id="89e3d-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e3d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e3d-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="89e3d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89e3d-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="89e3d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89e3d-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e3d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e3d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89e3d-137">See also</span></span>

- [<span data-ttu-id="89e3d-138">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="89e3d-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="89e3d-139">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="89e3d-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="89e3d-140">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="89e3d-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
