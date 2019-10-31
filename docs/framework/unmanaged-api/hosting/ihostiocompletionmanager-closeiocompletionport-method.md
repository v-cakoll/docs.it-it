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
ms.openlocfilehash: 254254af705f93793b030882e0ac79d0372ca55f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133885"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="50553-102">Metodo IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="50553-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="50553-103">Richiede che l'host chiuda una porta aperta tramite una chiamata precedente a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="50553-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50553-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50553-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50553-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50553-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="50553-106">in Handle della porta da chiudere.</span><span class="sxs-lookup"><span data-stu-id="50553-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50553-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="50553-107">Return Value</span></span>  
  
|<span data-ttu-id="50553-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50553-108">HRESULT</span></span>|<span data-ttu-id="50553-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50553-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50553-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50553-110">S_OK</span></span>|<span data-ttu-id="50553-111">`CloseIoCompletionPort` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="50553-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="50553-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50553-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50553-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="50553-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50553-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50553-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50553-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="50553-115">The call timed out.</span></span>|  
|<span data-ttu-id="50553-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50553-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50553-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="50553-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50553-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50553-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50553-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="50553-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50553-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50553-120">E_FAIL</span></span>|<span data-ttu-id="50553-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="50553-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50553-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="50553-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50553-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50553-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50553-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="50553-124">E_INVALIDARG</span></span>|<span data-ttu-id="50553-125">È stato passato un handle di porta non valido.</span><span class="sxs-lookup"><span data-stu-id="50553-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50553-126">Note</span><span class="sxs-lookup"><span data-stu-id="50553-126">Remarks</span></span>  
 <span data-ttu-id="50553-127">`hPort` deve essere un handle per una porta creata da una chiamata precedente a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="50553-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50553-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50553-128">Requirements</span></span>  
 <span data-ttu-id="50553-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50553-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50553-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50553-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50553-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50553-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50553-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50553-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50553-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50553-133">See also</span></span>

- [<span data-ttu-id="50553-134">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="50553-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="50553-135">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="50553-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
