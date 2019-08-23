---
title: Metodo ICLRRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fcadb708638efb0b7946426c538e01661505dfa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912247"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="e2a8a-102">Metodo ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="e2a8a-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e2a8a-103">Arresta l'esecuzione del codice da parte del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e2a8a-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e2a8a-104">Questo metodo non rilascia risorse nell'host, Scarica i domini applicazione o Elimina i thread.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="e2a8a-105">Per rilasciare queste risorse, è necessario terminare il processo.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a8a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2a8a-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e2a8a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2a8a-107">Return Value</span></span>  
  
|<span data-ttu-id="e2a8a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2a8a-108">HRESULT</span></span>|<span data-ttu-id="e2a8a-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e2a8a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2a8a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2a8a-110">S_OK</span></span>|<span data-ttu-id="e2a8a-111">`Stop`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="e2a8a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2a8a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2a8a-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2a8a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2a8a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2a8a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-115">The call timed out.</span></span>|  
|<span data-ttu-id="e2a8a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2a8a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2a8a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2a8a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2a8a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2a8a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2a8a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2a8a-120">E_FAIL</span></span>|<span data-ttu-id="e2a8a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2a8a-122">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2a8a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2a8a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2a8a-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2a8a-124">Requirements</span></span>  
 <span data-ttu-id="e2a8a-125">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2a8a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2a8a-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2a8a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2a8a-127">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2a8a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2a8a-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2a8a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a8a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a8a-129">See also</span></span>

- [<span data-ttu-id="e2a8a-130">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e2a8a-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
