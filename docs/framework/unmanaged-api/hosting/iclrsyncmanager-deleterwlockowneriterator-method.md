---
title: Metodo ICLRSyncManager::DeleteRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
ms.openlocfilehash: a4094a64d27072ce257341398bb49419bef9b8bb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763150"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="b0e00-102">Metodo ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="b0e00-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="b0e00-103">Richiede che il Common Language Runtime (CLR) elimini un iteratore creato da una chiamata a [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="b0e00-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0e00-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0e00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0e00-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="b0e00-106">in Iteratore creato tramite una chiamata a `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="b0e00-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0e00-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b0e00-107">Return Value</span></span>  
  
|<span data-ttu-id="b0e00-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0e00-108">HRESULT</span></span>|<span data-ttu-id="b0e00-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0e00-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0e00-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e00-110">S_OK</span></span>|<span data-ttu-id="b0e00-111">`DeleteRWLockOwnerIterator`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b0e00-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="b0e00-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0e00-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0e00-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b0e00-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="b0e00-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b0e00-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b0e00-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b0e00-115">The call timed out.</span></span>|  
|<span data-ttu-id="b0e00-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b0e00-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b0e00-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b0e00-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b0e00-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b0e00-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b0e00-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b0e00-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b0e00-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e00-120">E_FAIL</span></span>|<span data-ttu-id="b0e00-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b0e00-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0e00-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b0e00-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b0e00-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0e00-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0e00-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b0e00-124">Remarks</span></span>  
 <span data-ttu-id="b0e00-125">L'host può chiamare questo metodo e `CreateRWLockOwnerIterator` per garantire che l'implementazione del threading rimanga sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="b0e00-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e00-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0e00-126">Requirements</span></span>  
 <span data-ttu-id="b0e00-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e00-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e00-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b0e00-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0e00-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b0e00-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0e00-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e00-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e00-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0e00-131">See also</span></span>

- [<span data-ttu-id="b0e00-132">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b0e00-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b0e00-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b0e00-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
