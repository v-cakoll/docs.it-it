---
title: Metodo ICLRRuntimeHost::ExecuteInAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176422"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="521cb-102">Metodo ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="521cb-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="521cb-103">Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="521cb-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="521cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="521cb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="521cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="521cb-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="521cb-106">[in] ID numerico <xref:System.AppDomain> dell'oggetto in cui eseguire il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="521cb-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="521cb-107">[in] Puntatore alla funzione da eseguire <xref:System.AppDomain>all'interno dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="521cb-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="521cb-108">[in] Puntatore alla memoria opaca allocata dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="521cb-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="521cb-109">Questo parametro viene passato da Common Language Runtime (CLR) al callback di dominio.</span><span class="sxs-lookup"><span data-stu-id="521cb-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="521cb-110">Non è memoria heap gestita dal runtime; sia l'allocazione che la durata di questa memoria sono controllate dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="521cb-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="521cb-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="521cb-111">Return Value</span></span>  
  
|<span data-ttu-id="521cb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="521cb-112">HRESULT</span></span>|<span data-ttu-id="521cb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="521cb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="521cb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="521cb-114">S_OK</span></span>|<span data-ttu-id="521cb-115">`ExecuteInAppDomain`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="521cb-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="521cb-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="521cb-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="521cb-117">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="521cb-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="521cb-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="521cb-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="521cb-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="521cb-119">The call timed out.</span></span>|  
|<span data-ttu-id="521cb-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="521cb-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="521cb-121">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="521cb-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="521cb-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="521cb-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="521cb-123">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="521cb-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="521cb-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="521cb-124">E_FAIL</span></span>|<span data-ttu-id="521cb-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="521cb-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="521cb-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="521cb-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="521cb-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="521cb-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="521cb-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="521cb-128">Remarks</span></span>  
 <span data-ttu-id="521cb-129">`ExecuteInAppDomain`consente all'host di esercitare il controllo su cui gestito <xref:System.AppDomain> il metodo gestito specificato deve essere eseguito in.</span><span class="sxs-lookup"><span data-stu-id="521cb-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="521cb-130">È possibile ottenere il valore dell'identificatore di un dominio <xref:System.AppDomain.Id%2A> applicazione, che corrisponde al valore della proprietà, chiamando [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="521cb-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="521cb-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="521cb-131">Requirements</span></span>  
 <span data-ttu-id="521cb-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="521cb-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="521cb-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="521cb-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="521cb-134">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="521cb-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="521cb-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="521cb-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521cb-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="521cb-136">See also</span></span>

- [<span data-ttu-id="521cb-137">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="521cb-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
