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
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166972"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="638d6-102">Metodo ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="638d6-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="638d6-103">Arresta l'esecuzione di codice da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="638d6-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="638d6-104">Questo metodo non rilasciare le risorse nell'host, scaricare i domini applicazione o eliminare i thread.</span><span class="sxs-lookup"><span data-stu-id="638d6-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="638d6-105">È necessario terminare il processo di rilascio di queste risorse.</span><span class="sxs-lookup"><span data-stu-id="638d6-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="638d6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="638d6-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="638d6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="638d6-107">Return Value</span></span>  
  
|<span data-ttu-id="638d6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="638d6-108">HRESULT</span></span>|<span data-ttu-id="638d6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="638d6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="638d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="638d6-110">S_OK</span></span>|<span data-ttu-id="638d6-111">`Stop` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="638d6-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="638d6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="638d6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="638d6-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="638d6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="638d6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="638d6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="638d6-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="638d6-115">The call timed out.</span></span>|  
|<span data-ttu-id="638d6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="638d6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="638d6-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="638d6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="638d6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="638d6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="638d6-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="638d6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="638d6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="638d6-120">E_FAIL</span></span>|<span data-ttu-id="638d6-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="638d6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="638d6-122">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="638d6-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="638d6-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="638d6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="638d6-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="638d6-124">Requirements</span></span>  
 <span data-ttu-id="638d6-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="638d6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="638d6-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="638d6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="638d6-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="638d6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="638d6-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="638d6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638d6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="638d6-129">See also</span></span>

- [<span data-ttu-id="638d6-130">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="638d6-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
