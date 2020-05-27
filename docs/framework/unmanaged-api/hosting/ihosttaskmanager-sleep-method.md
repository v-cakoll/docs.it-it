---
title: Metodo IHostTaskManager::Sleep
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: bb12547155383bb410f592018232ca6f688bab8a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841906"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="fae57-102">Metodo IHostTaskManager::Sleep</span><span class="sxs-lookup"><span data-stu-id="fae57-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="fae57-103">Notifica all'host che l'attività corrente è in fase di sospensione.</span><span class="sxs-lookup"><span data-stu-id="fae57-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fae57-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fae57-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fae57-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="fae57-106">in Intervallo di tempo, in millisecondi, durante il quale il thread resterà in stato di sospensione.</span><span class="sxs-lookup"><span data-stu-id="fae57-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="fae57-107">in Uno dei valori di enumerazione [WAIT_OPTION](wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se questa azione si blocca.</span><span class="sxs-lookup"><span data-stu-id="fae57-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fae57-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fae57-108">Return Value</span></span>  
  
|<span data-ttu-id="fae57-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fae57-109">HRESULT</span></span>|<span data-ttu-id="fae57-110">Description</span><span class="sxs-lookup"><span data-stu-id="fae57-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fae57-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fae57-111">S_OK</span></span>|<span data-ttu-id="fae57-112">`Sleep`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="fae57-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="fae57-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fae57-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fae57-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="fae57-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fae57-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fae57-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fae57-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fae57-116">The call timed out.</span></span>|  
|<span data-ttu-id="fae57-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fae57-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fae57-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="fae57-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fae57-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fae57-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fae57-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fae57-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fae57-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fae57-121">E_FAIL</span></span>|<span data-ttu-id="fae57-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fae57-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fae57-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fae57-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fae57-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fae57-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fae57-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fae57-125">Remarks</span></span>  
 <span data-ttu-id="fae57-126">CLR chiama in genere `IHostTaskManager::Sleep` quando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> viene chiamato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="fae57-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fae57-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fae57-127">Requirements</span></span>  
 <span data-ttu-id="fae57-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fae57-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae57-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fae57-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fae57-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fae57-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fae57-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae57-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae57-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fae57-132">See also</span></span>

- [<span data-ttu-id="fae57-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fae57-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fae57-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fae57-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fae57-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="fae57-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fae57-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fae57-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
