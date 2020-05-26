---
title: Metodo IHostAutoEvent::Set
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 55fd858927743b097e5e842c0897a16d36b76733
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804978"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="f7f09-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="f7f09-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="f7f09-103">Imposta l'istanza corrente di [IHostAutoEvent](ihostautoevent-interface.md) su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="f7f09-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f09-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7f09-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f7f09-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f7f09-105">Return Value</span></span>  
  
|<span data-ttu-id="f7f09-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7f09-106">HRESULT</span></span>|<span data-ttu-id="f7f09-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7f09-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7f09-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7f09-108">S_OK</span></span>|<span data-ttu-id="f7f09-109">`Set`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f7f09-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="f7f09-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7f09-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7f09-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f7f09-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7f09-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7f09-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7f09-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f7f09-113">The call timed out.</span></span>|  
|<span data-ttu-id="f7f09-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7f09-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7f09-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f7f09-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7f09-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7f09-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7f09-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f7f09-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7f09-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7f09-118">E_FAIL</span></span>|<span data-ttu-id="f7f09-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f7f09-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7f09-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f7f09-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7f09-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f7f09-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7f09-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7f09-122">Requirements</span></span>  
 <span data-ttu-id="f7f09-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f09-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f09-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f7f09-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7f09-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f7f09-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7f09-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f09-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f09-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7f09-127">See also</span></span>

- [<span data-ttu-id="f7f09-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f7f09-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f7f09-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f7f09-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="f7f09-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="f7f09-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="f7f09-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f7f09-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
