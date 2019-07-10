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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e1a2358590b95b39b6495b74078f079c5b34876
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765684"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="d4cd5-102">Metodo ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d4cd5-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="d4cd5-103">Scarica managed <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4cd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4cd5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4cd5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4cd5-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d4cd5-106">[in] L'identificatore numerico del dominio dell'applicazione da scaricare.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="d4cd5-107">[in] `true` per indicare che common language runtime (CLR) è necessario attendere fino a quando non ha terminato l'esecuzione del thread dell'applicazione corrente prima di provare a scaricare il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4cd5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4cd5-108">Return Value</span></span>  
  
|<span data-ttu-id="d4cd5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4cd5-109">HRESULT</span></span>|<span data-ttu-id="d4cd5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4cd5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4cd5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4cd5-111">S_OK</span></span>|<span data-ttu-id="d4cd5-112">`UnloadAppDomain` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="d4cd5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d4cd5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d4cd5-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d4cd5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4cd5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d4cd5-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-116">The call timed out.</span></span>|  
|<span data-ttu-id="d4cd5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d4cd5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d4cd5-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d4cd5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d4cd5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d4cd5-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d4cd5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4cd5-121">E_FAIL</span></span>|<span data-ttu-id="d4cd5-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4cd5-123">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d4cd5-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4cd5-125">Note</span><span class="sxs-lookup"><span data-stu-id="d4cd5-125">Remarks</span></span>  
 <span data-ttu-id="d4cd5-126">È possibile ottenere l'identificatore numerico del dominio dell'applicazione in cui è in esecuzione il thread corrente chiamando [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="d4cd5-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="d4cd5-127">Questo identificatore corrisponde alla <xref:System.AppDomain.Id%2A> proprietà di gestito <xref:System.AppDomain> tipo.</span><span class="sxs-lookup"><span data-stu-id="d4cd5-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4cd5-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4cd5-128">Requirements</span></span>  
 <span data-ttu-id="d4cd5-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4cd5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4cd5-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4cd5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4cd5-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d4cd5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4cd5-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4cd5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cd5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4cd5-133">See also</span></span>

- [<span data-ttu-id="d4cd5-134">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d4cd5-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
