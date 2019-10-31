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
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120496"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="d8dfc-102">Metodo ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="d8dfc-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="d8dfc-103">Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dfc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8dfc-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8dfc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8dfc-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="d8dfc-106">in ID numerico del <xref:System.AppDomain> in cui eseguire il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="d8dfc-107">in Puntatore alla funzione da eseguire all'interno del <xref:System.AppDomain>specificato.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="d8dfc-108">in Puntatore alla memoria allocata dal chiamante opaco.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="d8dfc-109">Questo parametro viene passato dal Common Language Runtime (CLR) al callback del dominio.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="d8dfc-110">Non si tratta di memoria heap gestita dal runtime; sia l'allocazione che la durata della memoria sono controllate dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8dfc-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8dfc-111">Return Value</span></span>  
  
|<span data-ttu-id="d8dfc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8dfc-112">HRESULT</span></span>|<span data-ttu-id="d8dfc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8dfc-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8dfc-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8dfc-114">S_OK</span></span>|<span data-ttu-id="d8dfc-115">`ExecuteInAppDomain` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="d8dfc-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8dfc-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8dfc-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8dfc-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8dfc-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8dfc-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-119">The call timed out.</span></span>|  
|<span data-ttu-id="d8dfc-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8dfc-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8dfc-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8dfc-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8dfc-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8dfc-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8dfc-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8dfc-124">E_FAIL</span></span>|<span data-ttu-id="d8dfc-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8dfc-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8dfc-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8dfc-128">Note</span><span class="sxs-lookup"><span data-stu-id="d8dfc-128">Remarks</span></span>  
 <span data-ttu-id="d8dfc-129">`ExecuteInAppDomain` consente all'host di esercitare il controllo sulla <xref:System.AppDomain> gestita in cui deve essere eseguito il metodo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="d8dfc-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="d8dfc-130">È possibile ottenere il valore dell'identificatore di un dominio dell'applicazione, che corrisponde al valore della proprietà <xref:System.AppDomain.Id%2A>, chiamando il [Metodo GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="d8dfc-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8dfc-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8dfc-131">Requirements</span></span>  
 <span data-ttu-id="d8dfc-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8dfc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8dfc-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8dfc-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8dfc-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8dfc-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8dfc-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8dfc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dfc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8dfc-136">See also</span></span>

- [<span data-ttu-id="d8dfc-137">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d8dfc-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
