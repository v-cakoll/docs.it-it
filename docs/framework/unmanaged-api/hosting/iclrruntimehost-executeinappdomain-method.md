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
ms.openlocfilehash: 505c16cb7ead7950b6d2d6d401730cc3368fb6aa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703302"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="3093a-102">Metodo ICLRRuntimeHost::ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="3093a-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="3093a-103">Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="3093a-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3093a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3093a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3093a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3093a-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="3093a-106">in ID numerico dell'oggetto <xref:System.AppDomain> nel quale eseguire il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="3093a-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="3093a-107">in Puntatore alla funzione da eseguire all'interno dell'oggetto specificato <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="3093a-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="3093a-108">in Puntatore alla memoria allocata dal chiamante opaco.</span><span class="sxs-lookup"><span data-stu-id="3093a-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="3093a-109">Questo parametro viene passato dal Common Language Runtime (CLR) al callback del dominio.</span><span class="sxs-lookup"><span data-stu-id="3093a-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="3093a-110">Non si tratta di memoria heap gestita dal runtime; sia l'allocazione che la durata della memoria sono controllate dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="3093a-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3093a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3093a-111">Return Value</span></span>  
  
|<span data-ttu-id="3093a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3093a-112">HRESULT</span></span>|<span data-ttu-id="3093a-113">Description</span><span class="sxs-lookup"><span data-stu-id="3093a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3093a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3093a-114">S_OK</span></span>|<span data-ttu-id="3093a-115">`ExecuteInAppDomain`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3093a-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="3093a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3093a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3093a-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3093a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3093a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3093a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3093a-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3093a-119">The call timed out.</span></span>|  
|<span data-ttu-id="3093a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3093a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3093a-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="3093a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3093a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3093a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3093a-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3093a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3093a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3093a-124">E_FAIL</span></span>|<span data-ttu-id="3093a-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3093a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3093a-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3093a-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3093a-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3093a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3093a-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3093a-128">Remarks</span></span>  
 <span data-ttu-id="3093a-129">`ExecuteInAppDomain`consente all'host di esercitare il controllo su quale gestito <xref:System.AppDomain> deve essere eseguito il metodo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="3093a-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="3093a-130">È possibile ottenere il valore dell'identificatore di un dominio dell'applicazione, che corrisponde al valore della <xref:System.AppDomain.Id%2A> proprietà, chiamando il [Metodo GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="3093a-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3093a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3093a-131">Requirements</span></span>  
 <span data-ttu-id="3093a-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3093a-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3093a-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3093a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3093a-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3093a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3093a-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3093a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3093a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3093a-136">See also</span></span>

- [<span data-ttu-id="3093a-137">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3093a-137">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
