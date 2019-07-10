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
ms.openlocfilehash: 97a0e6cbbd8972f58f9eedcfeb8aff1f93694064
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765665"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="3c66d-102">Metodo ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="3c66d-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3c66d-103">Arresta l'esecuzione di codice da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3c66d-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c66d-104">Questo metodo non rilasciare le risorse nell'host, scaricare i domini applicazione o eliminare i thread.</span><span class="sxs-lookup"><span data-stu-id="3c66d-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="3c66d-105">È necessario terminare il processo di rilascio di queste risorse.</span><span class="sxs-lookup"><span data-stu-id="3c66d-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c66d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c66d-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3c66d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c66d-107">Return Value</span></span>  
  
|<span data-ttu-id="3c66d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c66d-108">HRESULT</span></span>|<span data-ttu-id="3c66d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c66d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c66d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c66d-110">S_OK</span></span>|<span data-ttu-id="3c66d-111">`Stop` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c66d-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="3c66d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c66d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c66d-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c66d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c66d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c66d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c66d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c66d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3c66d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c66d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c66d-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3c66d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c66d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c66d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c66d-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3c66d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c66d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c66d-120">E_FAIL</span></span>|<span data-ttu-id="3c66d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3c66d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c66d-122">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3c66d-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c66d-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c66d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c66d-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c66d-124">Requirements</span></span>  
 <span data-ttu-id="3c66d-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c66d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c66d-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c66d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c66d-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3c66d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c66d-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c66d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c66d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c66d-129">See also</span></span>

- [<span data-ttu-id="3c66d-130">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3c66d-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
