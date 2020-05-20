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
ms.openlocfilehash: 98af9931e219c384b017d3c70fe21cdb6e052ac1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615956"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="85513-102">Metodo ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="85513-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="85513-103">Ottiene un enumeratore [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) per le identità di assembly a cui fa riferimento l'assembly con il tipo di identità specificato.</span><span class="sxs-lookup"><span data-stu-id="85513-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85513-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85513-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85513-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85513-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="85513-106">in Valore valido che specifica l'architettura del processore, come definito in WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="85513-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="85513-107">in Fornito per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="85513-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="85513-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione corrente di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="85513-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="85513-109">in Identità di associazione di assembly opaca, in genere restituita da una chiamata al metodo [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) .</span><span class="sxs-lookup"><span data-stu-id="85513-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="85513-110">out Puntatore a un'interfaccia a un `ICLRProbingAssemblyEnum` enumeratore che contiene riferimenti agli assembly a cui fa riferimento l'assembly identificato da `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="85513-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85513-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="85513-111">Return Value</span></span>  
  
|<span data-ttu-id="85513-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85513-112">HRESULT</span></span>|<span data-ttu-id="85513-113">Description</span><span class="sxs-lookup"><span data-stu-id="85513-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85513-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="85513-114">S_OK</span></span>|<span data-ttu-id="85513-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="85513-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="85513-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85513-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85513-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="85513-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85513-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85513-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85513-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="85513-119">The call timed out.</span></span>|  
|<span data-ttu-id="85513-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85513-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85513-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="85513-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85513-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85513-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85513-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="85513-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85513-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85513-124">E_FAIL</span></span>|<span data-ttu-id="85513-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="85513-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85513-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="85513-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85513-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85513-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85513-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85513-128">Requirements</span></span>  
 <span data-ttu-id="85513-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85513-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85513-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85513-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85513-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="85513-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85513-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85513-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85513-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85513-133">See also</span></span>

- [<span data-ttu-id="85513-134">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="85513-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="85513-135">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="85513-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="85513-136">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="85513-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
