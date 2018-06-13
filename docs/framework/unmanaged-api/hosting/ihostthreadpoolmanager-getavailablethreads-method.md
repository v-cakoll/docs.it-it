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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8350140bb0871acc560163848ac50eafef42f01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441215"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="b7a37-102">Metodo IHostThreadPoolManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="b7a37-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="b7a37-103">Ottiene il numero di thread nel pool di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b7a37-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7a37-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7a37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7a37-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="b7a37-106">[out] Puntatore al numero di thread nel pool di thread che non stanno elaborando gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b7a37-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7a37-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b7a37-107">Return Value</span></span>  
  
|<span data-ttu-id="b7a37-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7a37-108">HRESULT</span></span>|<span data-ttu-id="b7a37-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7a37-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7a37-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7a37-110">S_OK</span></span>|<span data-ttu-id="b7a37-111">`GetAvailableThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b7a37-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b7a37-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7a37-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7a37-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7a37-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7a37-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7a37-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7a37-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7a37-115">The call timed out.</span></span>|  
|<span data-ttu-id="b7a37-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7a37-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7a37-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="b7a37-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7a37-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7a37-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7a37-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b7a37-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7a37-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7a37-120">E_FAIL</span></span>|<span data-ttu-id="b7a37-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b7a37-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7a37-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b7a37-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7a37-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7a37-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7a37-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b7a37-124">E_NOTIMPL</span></span>|<span data-ttu-id="b7a37-125">L'host non fornisce un'implementazione di `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b7a37-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a37-126">Note</span><span class="sxs-lookup"><span data-stu-id="b7a37-126">Remarks</span></span>  
 <span data-ttu-id="b7a37-127">Se l'host non fornisce un'implementazione di `GetAvailableThreads`, deve restituire un valore HRESULT di E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b7a37-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a37-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7a37-128">Requirements</span></span>  
 <span data-ttu-id="b7a37-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a37-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a37-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b7a37-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7a37-131">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b7a37-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7a37-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a37-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a37-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7a37-133">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="b7a37-134">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="b7a37-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
