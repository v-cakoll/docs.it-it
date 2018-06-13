---
title: Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49962e632ced9aac376791ead672e6910117ee10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434739"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="be4c8-102">Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="be4c8-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="be4c8-103">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) istanza dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="be4c8-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be4c8-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be4c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be4c8-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="be4c8-106">[in] Matrice di stringhe con terminazione null nel formato "proprietà name = value …" che consente di specificare un elenco di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="be4c8-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="be4c8-107">[in] Il numero di elementi in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="be4c8-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="be4c8-108">[out] Puntatore a interfaccia a un `ICLRAssemblyReferenceList` oggetto che contiene i dati di identità di assembly per l'elenco di assembly specificato in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="be4c8-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be4c8-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be4c8-109">Return Value</span></span>  
  
|<span data-ttu-id="be4c8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be4c8-110">HRESULT</span></span>|<span data-ttu-id="be4c8-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be4c8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be4c8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="be4c8-112">S_OK</span></span>|<span data-ttu-id="be4c8-113">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="be4c8-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="be4c8-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be4c8-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be4c8-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="be4c8-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be4c8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be4c8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be4c8-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="be4c8-117">The call timed out.</span></span>|  
|<span data-ttu-id="be4c8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be4c8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be4c8-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="be4c8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be4c8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be4c8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be4c8-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="be4c8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be4c8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be4c8-122">E_FAIL</span></span>|<span data-ttu-id="be4c8-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="be4c8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be4c8-124">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="be4c8-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be4c8-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="be4c8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be4c8-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be4c8-126">Requirements</span></span>  
 <span data-ttu-id="be4c8-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be4c8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4c8-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="be4c8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be4c8-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="be4c8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be4c8-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be4c8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4c8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be4c8-131">See Also</span></span>  
 [<span data-ttu-id="be4c8-132">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="be4c8-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="be4c8-133">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="be4c8-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
