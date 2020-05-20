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
ms.openlocfilehash: 5cf6f942add3d090cf830e71a545b9f4d4f69f00
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703171"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="eecda-102">Metodo ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="eecda-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="eecda-103">Specifica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="eecda-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eecda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eecda-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eecda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eecda-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="eecda-106">in Combinazione di valori [EApiCategories](eapicategories-enumeration.md) , che indica quali categorie di tipi e membri gestiti devono essere bloccate dall'esecuzione in codice parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="eecda-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eecda-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eecda-107">Return Value</span></span>  
  
|<span data-ttu-id="eecda-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eecda-108">HRESULT</span></span>|<span data-ttu-id="eecda-109">Description</span><span class="sxs-lookup"><span data-stu-id="eecda-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eecda-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eecda-110">S_OK</span></span>|<span data-ttu-id="eecda-111">`SetProtectedCategories`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="eecda-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="eecda-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eecda-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eecda-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="eecda-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eecda-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eecda-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eecda-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="eecda-115">The call timed out.</span></span>|  
|<span data-ttu-id="eecda-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eecda-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eecda-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="eecda-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eecda-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eecda-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eecda-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="eecda-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eecda-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eecda-120">E_FAIL</span></span>|<span data-ttu-id="eecda-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="eecda-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eecda-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="eecda-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eecda-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eecda-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eecda-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eecda-124">Remarks</span></span>  
 <span data-ttu-id="eecda-125">Ogni `EApiCategories` valore fa riferimento a un elenco di tipi e membri gestiti.</span><span class="sxs-lookup"><span data-stu-id="eecda-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="eecda-126">L' `EApiCategories` enumerazione e il `SetProtectedCategories` metodo sono direttamente correlati alla classe gestita <xref:System.Security.Permissions.HostProtectionAttribute> , che viene usata per contrassegnare i tipi e i membri gestiti che espongono funzionalità corrispondenti alle categorie descritte da `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="eecda-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="eecda-127">Per ulteriori informazioni, vedere <xref:System.Security.Permissions.HostProtectionAttribute> e l' <xref:System.Security.Permissions.HostProtectionResource> enumerazione, che corrisponde direttamente a `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="eecda-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eecda-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eecda-128">Requirements</span></span>  
 <span data-ttu-id="eecda-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eecda-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eecda-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eecda-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eecda-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eecda-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eecda-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eecda-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eecda-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eecda-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="eecda-134">Enumerazione EApiCategories</span><span class="sxs-lookup"><span data-stu-id="eecda-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="eecda-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="eecda-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="eecda-136">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="eecda-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
