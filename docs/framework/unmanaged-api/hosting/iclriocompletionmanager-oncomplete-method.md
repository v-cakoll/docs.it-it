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
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703821"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="0ca91-102">Metodo ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="0ca91-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="0ca91-103">Notifica al Common Language Runtime (CLR) lo stato di una richiesta di I/O effettuata mediante una chiamata al metodo [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ca91-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ca91-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ca91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ca91-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="0ca91-106">in Valore HRESULT che indica lo stato dell'operazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="0ca91-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="0ca91-107">S_OK indica che l'operazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0ca91-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="0ca91-108">HOST_E_INTERRUPTED indica che la chiamata è stata interrotta prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="0ca91-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="0ca91-109">E_FAIL indica che si è verificato un errore irreversibile sconosciuto, irreversibile.</span><span class="sxs-lookup"><span data-stu-id="0ca91-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="0ca91-110">in Numero di byte trasferiti durante l'elaborazione della richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="0ca91-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="0ca91-111">in Puntatore alla `OVERLAPPED` struttura passata alla chiamata al `IHostIoCompletionManager::Bind` metodo.</span><span class="sxs-lookup"><span data-stu-id="0ca91-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ca91-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0ca91-112">Return Value</span></span>  
  
|<span data-ttu-id="0ca91-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ca91-113">HRESULT</span></span>|<span data-ttu-id="0ca91-114">Description</span><span class="sxs-lookup"><span data-stu-id="0ca91-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ca91-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ca91-115">S_OK</span></span>|<span data-ttu-id="0ca91-116">`OnComplete`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0ca91-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="0ca91-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ca91-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ca91-118">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0ca91-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ca91-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ca91-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ca91-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0ca91-120">The call timed out.</span></span>|  
|<span data-ttu-id="0ca91-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ca91-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ca91-122">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0ca91-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ca91-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ca91-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ca91-124">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0ca91-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ca91-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ca91-125">E_FAIL</span></span>|<span data-ttu-id="0ca91-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0ca91-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ca91-127">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0ca91-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ca91-128">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0ca91-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ca91-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0ca91-129">Remarks</span></span>  
 <span data-ttu-id="0ca91-130">Se l'host implementa un'astrazione di completamento I/O, CLR esegue le richieste I/O attraverso l'host usando i metodi di [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0ca91-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="0ca91-131">L'host chiama quindi il `OnComplete` metodo per notificare al runtime il risultato di tali richieste.</span><span class="sxs-lookup"><span data-stu-id="0ca91-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca91-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ca91-132">Requirements</span></span>  
 <span data-ttu-id="0ca91-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ca91-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca91-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0ca91-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ca91-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ca91-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ca91-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca91-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca91-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ca91-137">See also</span></span>

- [<span data-ttu-id="0ca91-138">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0ca91-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0ca91-139">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0ca91-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="0ca91-140">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="0ca91-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
