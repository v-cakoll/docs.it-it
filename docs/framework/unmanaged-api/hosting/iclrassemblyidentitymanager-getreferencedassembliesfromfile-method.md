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
ms.openlocfilehash: 3c4f673d88594e86004c6d51a4d58a0ac4642875
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615943"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="2bd8f-102">Metodo ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="2bd8f-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="2bd8f-103">Ottiene un'istanza di [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-103">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bd8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bd8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bd8f-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="2bd8f-106">in Percorso dell'assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2bd8f-107">in Fornito per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="2bd8f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione corrente di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2bd8f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="2bd8f-109">in Puntatore a un oggetto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che rappresenta gli assembly da escludere da `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="2bd8f-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="2bd8f-110">out Puntatore all'indirizzo di un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly in `pwzFilePath` , esclusi gli assembly rappresentati da `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="2bd8f-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bd8f-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2bd8f-111">Return Value</span></span>  
  
|<span data-ttu-id="2bd8f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2bd8f-112">HRESULT</span></span>|<span data-ttu-id="2bd8f-113">Description</span><span class="sxs-lookup"><span data-stu-id="2bd8f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2bd8f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bd8f-114">S_OK</span></span>|<span data-ttu-id="2bd8f-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="2bd8f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2bd8f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2bd8f-117">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2bd8f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2bd8f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2bd8f-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-119">The call timed out.</span></span>|  
|<span data-ttu-id="2bd8f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2bd8f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2bd8f-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2bd8f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2bd8f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2bd8f-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2bd8f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2bd8f-124">E_FAIL</span></span>|<span data-ttu-id="2bd8f-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2bd8f-126">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2bd8f-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bd8f-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2bd8f-128">Remarks</span></span>  
 <span data-ttu-id="2bd8f-129">Il chiamante può scegliere di escludere un set di riferimenti ad assembly noti dall'elenco restituito.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="2bd8f-130">Questo set viene definito dal `pExcludeAssembliesList` parametro.</span><span class="sxs-lookup"><span data-stu-id="2bd8f-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bd8f-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bd8f-131">Requirements</span></span>  
 <span data-ttu-id="2bd8f-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bd8f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd8f-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2bd8f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bd8f-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2bd8f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bd8f-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd8f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd8f-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bd8f-136">See also</span></span>

- [<span data-ttu-id="2bd8f-137">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="2bd8f-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="2bd8f-138">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="2bd8f-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="2bd8f-139">Interfaccia ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="2bd8f-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
