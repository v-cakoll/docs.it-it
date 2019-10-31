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
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133905"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="6fcc3-102">Metodo IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="6fcc3-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="6fcc3-103">Associa l'handle specificato a una porta di completamento di I/O creata da una chiamata precedente a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="6fcc3-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fcc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fcc3-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fcc3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fcc3-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="6fcc3-106">in Porta di completamento I/O a cui associare `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="6fcc3-107">Se il valore di `hPort` è null, `hHandle` viene associato alla porta di completamento I/O predefinita.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="6fcc3-108">in Handle del sistema operativo da associare a `hPort`.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fcc3-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6fcc3-109">Return Value</span></span>  
  
|<span data-ttu-id="6fcc3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fcc3-110">HRESULT</span></span>|<span data-ttu-id="6fcc3-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fcc3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fcc3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fcc3-112">S_OK</span></span>|<span data-ttu-id="6fcc3-113">`Bind` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="6fcc3-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fcc3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fcc3-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fcc3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fcc3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fcc3-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-117">The call timed out.</span></span>|  
|<span data-ttu-id="6fcc3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fcc3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fcc3-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fcc3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fcc3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fcc3-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fcc3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fcc3-122">E_FAIL</span></span>|<span data-ttu-id="6fcc3-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fcc3-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fcc3-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fcc3-126">Note</span><span class="sxs-lookup"><span data-stu-id="6fcc3-126">Remarks</span></span>  
 <span data-ttu-id="6fcc3-127">Viene creata una porta di completamento di I/O tramite una chiamata a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="6fcc3-128">CLR chiama `Bind` per associare un handle a tale porta.</span><span class="sxs-lookup"><span data-stu-id="6fcc3-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fcc3-129">Quando una richiesta di I/O viene completata, l'host deve chiamare il metodo [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6fcc3-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fcc3-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fcc3-130">Requirements</span></span>  
 <span data-ttu-id="6fcc3-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fcc3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fcc3-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6fcc3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fcc3-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6fcc3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fcc3-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fcc3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fcc3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fcc3-135">See also</span></span>

- [<span data-ttu-id="6fcc3-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="6fcc3-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
