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
ms.openlocfilehash: de166a22350e49197ff6a5b5d6dc956cdcc2d1ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089510"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="b38f7-102">Metodo ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="b38f7-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="b38f7-103">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) istanza dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="b38f7-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b38f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b38f7-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b38f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b38f7-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="b38f7-106">[in] Matrice di stringhe con terminazione null nella forma "proprietà nome = valore..." che specifica un elenco delle identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="b38f7-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="b38f7-107">[in] Il numero di elementi in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="b38f7-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="b38f7-108">[out] Puntatore a interfaccia a un `ICLRAssemblyReferenceList` oggetto che contiene i dati di identità di assembly per un elenco di assembly specificati in `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="b38f7-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b38f7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b38f7-109">Return Value</span></span>  
  
|<span data-ttu-id="b38f7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b38f7-110">HRESULT</span></span>|<span data-ttu-id="b38f7-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b38f7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b38f7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b38f7-112">S_OK</span></span>|<span data-ttu-id="b38f7-113">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b38f7-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="b38f7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b38f7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b38f7-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b38f7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b38f7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b38f7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b38f7-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b38f7-117">The call timed out.</span></span>|  
|<span data-ttu-id="b38f7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b38f7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b38f7-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b38f7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b38f7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b38f7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b38f7-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b38f7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b38f7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b38f7-122">E_FAIL</span></span>|<span data-ttu-id="b38f7-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b38f7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b38f7-124">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b38f7-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b38f7-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b38f7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b38f7-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b38f7-126">Requirements</span></span>  
 <span data-ttu-id="b38f7-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b38f7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b38f7-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b38f7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b38f7-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b38f7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b38f7-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b38f7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38f7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b38f7-131">See also</span></span>

- [<span data-ttu-id="b38f7-132">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="b38f7-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b38f7-133">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="b38f7-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
