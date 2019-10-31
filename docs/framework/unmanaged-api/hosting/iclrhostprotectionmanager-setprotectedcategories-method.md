---
title: Metodo ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141045"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="4e3a4-102">Metodo ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="4e3a4-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="4e3a4-103">Specifica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e3a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e3a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e3a4-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="4e3a4-106">in Combinazione di valori [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) , che indica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3a4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e3a4-107">Return Value</span></span>  
  
|<span data-ttu-id="4e3a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e3a4-108">HRESULT</span></span>|<span data-ttu-id="4e3a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e3a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e3a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e3a4-110">S_OK</span></span>|<span data-ttu-id="4e3a4-111">`SetProtectedCategories` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="4e3a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e3a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e3a4-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e3a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e3a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e3a4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="4e3a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e3a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e3a4-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e3a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e3a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e3a4-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e3a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e3a4-120">E_FAIL</span></span>|<span data-ttu-id="4e3a4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e3a4-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e3a4-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e3a4-124">Note</span><span class="sxs-lookup"><span data-stu-id="4e3a4-124">Remarks</span></span>  
 <span data-ttu-id="4e3a4-125">Ogni valore `EApiCategories` fa riferimento a un elenco di tipi e membri gestiti.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="4e3a4-126">L'enumerazione `EApiCategories` e il metodo `SetProtectedCategories` sono direttamente correlati alla classe <xref:System.Security.Permissions.HostProtectionAttribute> gestita, che viene utilizzata per contrassegnare i tipi e i membri gestiti che espongono le funzionalità corrispondenti alle categorie descritte da `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="4e3a4-127">Per ulteriori informazioni, vedere <xref:System.Security.Permissions.HostProtectionAttribute> e l'enumerazione <xref:System.Security.Permissions.HostProtectionResource>, che corrisponde direttamente al `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="4e3a4-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3a4-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e3a4-128">Requirements</span></span>  
 <span data-ttu-id="4e3a4-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e3a4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3a4-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e3a4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e3a4-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e3a4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e3a4-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3a4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3a4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3a4-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="4e3a4-134">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="4e3a4-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="4e3a4-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4e3a4-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="4e3a4-136">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="4e3a4-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
