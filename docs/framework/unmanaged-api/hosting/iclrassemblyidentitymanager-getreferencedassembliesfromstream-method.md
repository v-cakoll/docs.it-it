---
title: Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35f7e168f143d9427bf6905e9b4c383d9a40cd1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514452"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="e1e0d-102">Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="e1e0d-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="e1e0d-103">Ottiene un puntatore a un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) oggetto contenente i dati di identità di assembly per gli assembly a cui fatto riferimento l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e0d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1e0d-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1e0d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1e0d-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="e1e0d-106">[in] Un puntatore a interfaccia per un `IStream` contenente l'assembly deve essere valutata.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e1e0d-107">[in] Fornito per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="e1e0d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che supporta la versione corrente di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1e0d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="e1e0d-109">[in] Un puntatore a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) oggetto contenente i dati di identità di assembly per gli assembly da escludere dalle `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="e1e0d-110">[out] Un puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto contenente i dati di identità di assembly per gli assembly a cui fatto riferimento all'assembly nel `pStream`, esclusi gli assembly in `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1e0d-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1e0d-111">Return Value</span></span>  
  
|<span data-ttu-id="e1e0d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1e0d-112">HRESULT</span></span>|<span data-ttu-id="e1e0d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1e0d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1e0d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1e0d-114">S_OK</span></span>|<span data-ttu-id="e1e0d-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="e1e0d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1e0d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1e0d-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1e0d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1e0d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1e0d-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-119">The call timed out.</span></span>|  
|<span data-ttu-id="e1e0d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1e0d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1e0d-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1e0d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1e0d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1e0d-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1e0d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1e0d-124">E_FAIL</span></span>|<span data-ttu-id="e1e0d-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1e0d-126">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1e0d-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e0d-128">Note</span><span class="sxs-lookup"><span data-stu-id="e1e0d-128">Remarks</span></span>  
 <span data-ttu-id="e1e0d-129">Il chiamante può scegliere di escludere un insieme di riferimenti ad assembly noti nell'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="e1e0d-130">Questo set è definito da `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="e1e0d-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e0d-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1e0d-131">Requirements</span></span>  
 <span data-ttu-id="e1e0d-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e0d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e0d-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1e0d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1e0d-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e1e0d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1e0d-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e0d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e0d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1e0d-136">See also</span></span>
- [<span data-ttu-id="e1e0d-137">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="e1e0d-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e1e0d-138">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e1e0d-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e1e0d-139">Interfaccia ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e1e0d-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
