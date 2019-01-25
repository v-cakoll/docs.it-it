---
title: Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b3c727b49b7df48baa4f5084106f0586419133e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625696"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="0c20a-102">Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="0c20a-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="0c20a-103">Ottiene un' [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) istanza che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso file specificato.</span><span class="sxs-lookup"><span data-stu-id="0c20a-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c20a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c20a-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c20a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c20a-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="0c20a-106">[in] Il percorso dell'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="0c20a-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0c20a-107">[in] Fornito per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="0c20a-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="0c20a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che supporta la versione corrente di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0c20a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="0c20a-109">[in] Un puntatore a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta gli assembly che devono essere esclusi dalla `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="0c20a-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="0c20a-110">[out] Un puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto contenente i dati di identità di assembly per gli assembly a cui fatto riferimento all'assembly in `pwzFilePath`, esclusi gli assembly rappresentati da `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="0c20a-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c20a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c20a-111">Return Value</span></span>  
  
|<span data-ttu-id="0c20a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c20a-112">HRESULT</span></span>|<span data-ttu-id="0c20a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c20a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c20a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c20a-114">S_OK</span></span>|<span data-ttu-id="0c20a-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c20a-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="0c20a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c20a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c20a-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c20a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c20a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c20a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c20a-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c20a-119">The call timed out.</span></span>|  
|<span data-ttu-id="0c20a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c20a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c20a-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="0c20a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c20a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c20a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c20a-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0c20a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c20a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c20a-124">E_FAIL</span></span>|<span data-ttu-id="0c20a-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0c20a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c20a-126">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0c20a-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c20a-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c20a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c20a-128">Note</span><span class="sxs-lookup"><span data-stu-id="0c20a-128">Remarks</span></span>  
 <span data-ttu-id="0c20a-129">Il chiamante può scegliere di escludere un insieme di riferimenti ad assembly noti nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="0c20a-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="0c20a-130">Questo set è definito dal `pExcludeAssembliesList` parametro.</span><span class="sxs-lookup"><span data-stu-id="0c20a-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c20a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c20a-131">Requirements</span></span>  
 <span data-ttu-id="0c20a-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c20a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c20a-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c20a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c20a-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0c20a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c20a-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c20a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c20a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c20a-136">See also</span></span>
- [<span data-ttu-id="0c20a-137">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="0c20a-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="0c20a-138">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="0c20a-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0c20a-139">Interfaccia ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="0c20a-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
