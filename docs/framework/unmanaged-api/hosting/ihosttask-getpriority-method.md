---
title: Metodo IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 317223b1ce42924fcd20c44f791b0a24836a3ff8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442189"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="0b4b7-102">Metodo IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="0b4b7-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="0b4b7-103">Ottiene il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b4b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b4b7-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b4b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b4b7-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="0b4b7-106">[out] Un puntatore a un intero che indica il livello di priorità di thread per l'attività rappresentata dall'oggetto corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b4b7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b4b7-107">Return Value</span></span>  
  
|<span data-ttu-id="0b4b7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b4b7-108">HRESULT</span></span>|<span data-ttu-id="0b4b7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b4b7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b4b7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b4b7-110">S_OK</span></span>|<span data-ttu-id="0b4b7-111">`GetPriority` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="0b4b7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b4b7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b4b7-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b4b7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b4b7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b4b7-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-115">The call timed out.</span></span>|  
|<span data-ttu-id="0b4b7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b4b7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b4b7-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b4b7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b4b7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b4b7-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b4b7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b4b7-120">E_FAIL</span></span>|<span data-ttu-id="0b4b7-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b4b7-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b4b7-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b4b7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b4b7-124">Note</span><span class="sxs-lookup"><span data-stu-id="0b4b7-124">Remarks</span></span>  
 <span data-ttu-id="0b4b7-125">I valori del livello di priorità del thread sono definiti da Win32 `SetThreadPriority` (funzione).</span><span class="sxs-lookup"><span data-stu-id="0b4b7-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b4b7-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b4b7-126">Requirements</span></span>  
 <span data-ttu-id="0b4b7-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b4b7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b4b7-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0b4b7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b4b7-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0b4b7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b4b7-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b4b7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4b7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b4b7-131">See Also</span></span>  
 [<span data-ttu-id="0b4b7-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0b4b7-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0b4b7-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0b4b7-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0b4b7-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="0b4b7-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0b4b7-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0b4b7-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
