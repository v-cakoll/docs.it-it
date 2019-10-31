---
title: Metodo ICLRRuntimeHost::UnloadAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 2a6dc878f156d5d18970fed72c9722bab60f9ba8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120400"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="e5e8a-102">Metodo ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="e5e8a-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="e5e8a-103">Scarica il <xref:System.AppDomain> gestito che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5e8a-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5e8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5e8a-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="e5e8a-106">in Identificatore numerico del dominio dell'applicazione da scaricare.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="e5e8a-107">[in] `true` per indicare che l'Common Language Runtime (CLR) deve attendere il completamento dell'esecuzione del thread corrente dell'applicazione prima di tentare di scaricare il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5e8a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e5e8a-108">Return Value</span></span>  
  
|<span data-ttu-id="e5e8a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5e8a-109">HRESULT</span></span>|<span data-ttu-id="e5e8a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5e8a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5e8a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5e8a-111">S_OK</span></span>|<span data-ttu-id="e5e8a-112">`UnloadAppDomain` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="e5e8a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5e8a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5e8a-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5e8a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5e8a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5e8a-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-116">The call timed out.</span></span>|  
|<span data-ttu-id="e5e8a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5e8a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5e8a-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5e8a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5e8a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5e8a-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5e8a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5e8a-121">E_FAIL</span></span>|<span data-ttu-id="e5e8a-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5e8a-123">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5e8a-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5e8a-125">Note</span><span class="sxs-lookup"><span data-stu-id="e5e8a-125">Remarks</span></span>  
 <span data-ttu-id="e5e8a-126">È possibile ottenere l'identificatore numerico del dominio dell'applicazione in cui è in esecuzione il thread corrente chiamando [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5e8a-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="e5e8a-127">Questo identificatore corrisponde alla proprietà <xref:System.AppDomain.Id%2A> del tipo di <xref:System.AppDomain> gestito.</span><span class="sxs-lookup"><span data-stu-id="e5e8a-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e8a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5e8a-128">Requirements</span></span>  
 <span data-ttu-id="e5e8a-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5e8a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e8a-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e5e8a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5e8a-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e5e8a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5e8a-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e8a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e8a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5e8a-133">See also</span></span>

- [<span data-ttu-id="e5e8a-134">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e5e8a-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
