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
ms.openlocfilehash: 8d18e6c1dca7f52b17c19f4638410a08866905f7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804807"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="1203e-102">Metodo IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="1203e-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="1203e-103">Associa l'handle specificato a una porta di completamento di I/O creata da una chiamata precedente a [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="1203e-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1203e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1203e-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1203e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1203e-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="1203e-106">in Porta di completamento I/O a cui eseguire l'associazione `hHandle` .</span><span class="sxs-lookup"><span data-stu-id="1203e-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="1203e-107">Se il valore di `hPort` è null, `hHandle` viene associato alla porta di completamento i/O predefinita.</span><span class="sxs-lookup"><span data-stu-id="1203e-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="1203e-108">in Handle del sistema operativo a cui eseguire l'associazione `hPort` .</span><span class="sxs-lookup"><span data-stu-id="1203e-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1203e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1203e-109">Return Value</span></span>  
  
|<span data-ttu-id="1203e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1203e-110">HRESULT</span></span>|<span data-ttu-id="1203e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1203e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1203e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1203e-112">S_OK</span></span>|<span data-ttu-id="1203e-113">`Bind`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1203e-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="1203e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1203e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1203e-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1203e-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1203e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1203e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1203e-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1203e-117">The call timed out.</span></span>|  
|<span data-ttu-id="1203e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1203e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1203e-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="1203e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1203e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1203e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1203e-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1203e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1203e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1203e-122">E_FAIL</span></span>|<span data-ttu-id="1203e-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1203e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1203e-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1203e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1203e-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1203e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1203e-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1203e-126">Remarks</span></span>  
 <span data-ttu-id="1203e-127">Viene creata una porta di completamento di I/O tramite una chiamata a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="1203e-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="1203e-128">CLR chiama `Bind` per associare un handle a tale porta.</span><span class="sxs-lookup"><span data-stu-id="1203e-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1203e-129">Quando una richiesta di I/O viene completata, l'host deve chiamare il metodo [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1203e-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1203e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1203e-130">Requirements</span></span>  
 <span data-ttu-id="1203e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1203e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1203e-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1203e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1203e-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1203e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1203e-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1203e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1203e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1203e-135">See also</span></span>

- [<span data-ttu-id="1203e-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="1203e-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
