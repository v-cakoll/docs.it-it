---
title: Metodo ICLRControl::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: be29a4f83901b8e8fc338c2daa8f5703523402b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126580"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="e2054-102">Metodo ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="e2054-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="e2054-103">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo per i gestori del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2054-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2054-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2054-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2054-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2054-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="e2054-106">in Nome dell'assembly in cui viene implementato il tipo richiesto derivato da <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="e2054-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="e2054-107">in Nome del tipo implementato nel parametro `pwzAppDomainManagerAssembly` che implementa le funzionalità di <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="e2054-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2054-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2054-108">Return Value</span></span>  
  
|<span data-ttu-id="e2054-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2054-109">HRESULT</span></span>|<span data-ttu-id="e2054-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2054-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2054-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2054-111">S_OK</span></span>|<span data-ttu-id="e2054-112">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2054-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="e2054-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2054-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2054-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2054-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2054-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2054-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2054-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e2054-116">The call timed out.</span></span>|  
|<span data-ttu-id="e2054-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2054-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2054-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e2054-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2054-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2054-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2054-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e2054-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2054-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2054-121">E_FAIL</span></span>|<span data-ttu-id="e2054-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e2054-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2054-123">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e2054-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2054-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2054-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2054-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2054-125">Requirements</span></span>  
 <span data-ttu-id="e2054-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2054-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2054-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2054-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2054-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2054-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2054-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2054-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2054-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2054-130">See also</span></span>

- [<span data-ttu-id="e2054-131">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e2054-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e2054-132">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="e2054-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
