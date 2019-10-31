---
title: Metodo IHostThreadPoolManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 21449d9365e6260267d3c79f384f6136ce894821
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122088"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="c44a4-102">Metodo IHostThreadPoolManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="c44a4-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="c44a4-103">Ottiene il numero di thread nel pool di thread che non stanno attualmente elaborando elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c44a4-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c44a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c44a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c44a4-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="c44a4-106">out Puntatore al numero di thread nel pool di thread che non stanno attualmente elaborando elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c44a4-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c44a4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c44a4-107">Return Value</span></span>  
  
|<span data-ttu-id="c44a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c44a4-108">HRESULT</span></span>|<span data-ttu-id="c44a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c44a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c44a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c44a4-110">S_OK</span></span>|<span data-ttu-id="c44a4-111">`GetAvailableThreads` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c44a4-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c44a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c44a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c44a4-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c44a4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c44a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c44a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c44a4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c44a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="c44a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c44a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c44a4-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c44a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c44a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c44a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c44a4-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c44a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c44a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c44a4-120">E_FAIL</span></span>|<span data-ttu-id="c44a4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c44a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c44a4-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c44a4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c44a4-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c44a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c44a4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c44a4-124">E_NOTIMPL</span></span>|<span data-ttu-id="c44a4-125">L'host non fornisce un'implementazione di `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="c44a4-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c44a4-126">Note</span><span class="sxs-lookup"><span data-stu-id="c44a4-126">Remarks</span></span>  
 <span data-ttu-id="c44a4-127">Se l'host non fornisce un'implementazione di `GetAvailableThreads`, deve restituire un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c44a4-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44a4-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c44a4-128">Requirements</span></span>  
 <span data-ttu-id="c44a4-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44a4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44a4-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c44a4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c44a4-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c44a4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c44a4-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44a4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44a4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c44a4-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c44a4-134">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c44a4-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
