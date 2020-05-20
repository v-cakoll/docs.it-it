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
ms.openlocfilehash: 4f06dd7b85446eec986055418d2cf558b9b5bd7a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615930"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="7a7c7-102">Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="7a7c7-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="7a7c7-103">Ottiene un puntatore a un oggetto [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a7c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a7c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a7c7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a7c7-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="7a7c7-106">in Puntatore a un'interfaccia `IStream` contenente l'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7a7c7-107">in Fornito per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="7a7c7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione corrente di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7a7c7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="7a7c7-109">in Puntatore a un oggetto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che contiene i dati di identità dell'assembly per gli assembly da escludere `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="7a7c7-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="7a7c7-110">out Puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly in `pStream` , esclusi gli assembly in `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="7a7c7-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a7c7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a7c7-111">Return Value</span></span>  
  
|<span data-ttu-id="7a7c7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a7c7-112">HRESULT</span></span>|<span data-ttu-id="7a7c7-113">Description</span><span class="sxs-lookup"><span data-stu-id="7a7c7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a7c7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a7c7-114">S_OK</span></span>|<span data-ttu-id="7a7c7-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="7a7c7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a7c7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a7c7-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a7c7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a7c7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a7c7-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-119">The call timed out.</span></span>|  
|<span data-ttu-id="7a7c7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a7c7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a7c7-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a7c7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a7c7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a7c7-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a7c7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a7c7-124">E_FAIL</span></span>|<span data-ttu-id="7a7c7-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a7c7-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a7c7-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a7c7-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7a7c7-128">Remarks</span></span>  
 <span data-ttu-id="7a7c7-129">Il chiamante può scegliere di escludere un set di riferimenti ad assembly noti dall'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="7a7c7-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="7a7c7-130">Questo set è definito da `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="7a7c7-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a7c7-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a7c7-131">Requirements</span></span>  
 <span data-ttu-id="7a7c7-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a7c7-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a7c7-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7a7c7-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a7c7-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7a7c7-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a7c7-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a7c7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7c7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a7c7-136">See also</span></span>

- [<span data-ttu-id="7a7c7-137">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="7a7c7-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="7a7c7-138">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="7a7c7-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7a7c7-139">Interfaccia ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="7a7c7-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
