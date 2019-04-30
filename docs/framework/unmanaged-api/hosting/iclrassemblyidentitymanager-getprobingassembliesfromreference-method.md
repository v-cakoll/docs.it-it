---
title: Metodo ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e926fb2753367370e9aca726806eb8747e32048
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985127"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="f5039-102">Metodo ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="f5039-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="f5039-103">Ottiene un' [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumeratore per le identità di assembly a cui fanno riferimento all'assembly con il tipo di identità specificato.</span><span class="sxs-lookup"><span data-stu-id="f5039-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5039-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5039-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5039-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5039-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="f5039-106">[in] Un valore valido che specifica l'architettura del processore, come definito in Winnt. H.</span><span class="sxs-lookup"><span data-stu-id="f5039-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f5039-107">[in] Fornito per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="f5039-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="f5039-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che supporta la versione corrente di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f5039-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="f5039-109">[in] Un'identità di associazione di assembly opaco, in genere restituita da una chiamata ai [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="f5039-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="f5039-110">[out] Puntatore a interfaccia a un `ICLRProbingAssemblyEnum` enumeratore che contiene riferimenti agli assembly a cui fa riferimento l'assembly identificato dal `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f5039-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5039-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f5039-111">Return Value</span></span>  
  
|<span data-ttu-id="f5039-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5039-112">HRESULT</span></span>|<span data-ttu-id="f5039-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5039-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5039-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5039-114">S_OK</span></span>|<span data-ttu-id="f5039-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f5039-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="f5039-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5039-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5039-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5039-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5039-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5039-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5039-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5039-119">The call timed out.</span></span>|  
|<span data-ttu-id="f5039-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5039-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5039-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="f5039-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5039-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5039-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5039-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f5039-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5039-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5039-124">E_FAIL</span></span>|<span data-ttu-id="f5039-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f5039-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5039-126">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f5039-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5039-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5039-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5039-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5039-128">Requirements</span></span>  
 <span data-ttu-id="f5039-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5039-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5039-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5039-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5039-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f5039-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5039-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5039-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5039-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5039-133">See also</span></span>

- [<span data-ttu-id="f5039-134">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f5039-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f5039-135">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f5039-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f5039-136">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f5039-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
