---
title: Metodo IHostSecurityContext::Capture
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501521"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="31957-102">Metodo IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="31957-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="31957-103">Ottiene un clone dell'istanza di [IHostSecurityContext](ihostsecuritycontext-interface.md) restituita da una chiamata a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="31957-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31957-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31957-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31957-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31957-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="31957-106">out Puntatore all'indirizzo di un clone dell' `IHostSecurityContext` oggetto da acquisire.</span><span class="sxs-lookup"><span data-stu-id="31957-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31957-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="31957-107">Return Value</span></span>  
  
|<span data-ttu-id="31957-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31957-108">HRESULT</span></span>|<span data-ttu-id="31957-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31957-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31957-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="31957-110">S_OK</span></span>|<span data-ttu-id="31957-111">`Capture`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="31957-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="31957-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31957-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31957-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="31957-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31957-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31957-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31957-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="31957-115">The call timed out.</span></span>|  
|<span data-ttu-id="31957-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31957-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31957-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="31957-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31957-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31957-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31957-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="31957-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31957-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31957-120">E_FAIL</span></span>|<span data-ttu-id="31957-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="31957-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31957-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="31957-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31957-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="31957-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31957-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="31957-124">Remarks</span></span>  
 <span data-ttu-id="31957-125">Il puntatore di interfaccia restituito da `Capture` è un clone del contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="31957-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="31957-126">Quando queste informazioni vengono spostate in un punto di codice asincrono, la relativa durata è separata da quella dell'indicatore di misura in cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="31957-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="31957-127">Il puntatore originale può pertanto essere rilasciato.</span><span class="sxs-lookup"><span data-stu-id="31957-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31957-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31957-128">Requirements</span></span>  
 <span data-ttu-id="31957-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31957-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31957-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="31957-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31957-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31957-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31957-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31957-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31957-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31957-133">See also</span></span>

- [<span data-ttu-id="31957-134">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="31957-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="31957-135">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="31957-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
