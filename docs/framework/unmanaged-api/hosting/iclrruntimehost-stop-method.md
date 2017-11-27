---
title: Metodo ICLRRuntimeHost::Stop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3798c4fc451b78257373c0ac47a5e7e7c27dd048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="03f43-102">Metodo ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="03f43-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="03f43-103">Arresta l'esecuzione di codice da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="03f43-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03f43-104">Questo metodo non rilasciare le risorse nell'host, scaricare domini applicazioni o eliminare i thread.</span><span class="sxs-lookup"><span data-stu-id="03f43-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="03f43-105">È necessario terminare il processo per rilasciare le risorse.</span><span class="sxs-lookup"><span data-stu-id="03f43-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f43-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03f43-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="03f43-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="03f43-107">Return Value</span></span>  
  
|<span data-ttu-id="03f43-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03f43-108">HRESULT</span></span>|<span data-ttu-id="03f43-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03f43-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03f43-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="03f43-110">S_OK</span></span>|<span data-ttu-id="03f43-111">`Stop`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="03f43-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="03f43-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03f43-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03f43-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="03f43-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03f43-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03f43-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03f43-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="03f43-115">The call timed out.</span></span>|  
|<span data-ttu-id="03f43-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03f43-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03f43-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="03f43-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03f43-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03f43-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03f43-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="03f43-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03f43-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03f43-120">E_FAIL</span></span>|<span data-ttu-id="03f43-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="03f43-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03f43-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="03f43-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03f43-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03f43-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03f43-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03f43-124">Requirements</span></span>  
 <span data-ttu-id="03f43-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f43-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f43-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="03f43-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03f43-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03f43-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03f43-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03f43-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f43-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f43-129">See Also</span></span>  
 [<span data-ttu-id="03f43-130">ICLRRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="03f43-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
