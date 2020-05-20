---
title: Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 5b537d59014afa783d3f8c5046cc02dad7ea7740
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615995"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="953c4-102">Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="953c4-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="953c4-103">Ottiene i dati dell'associazione di identità dell'assembly per l'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="953c4-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="953c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="953c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="953c4-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="953c4-106">in Percorso del file da valutare.</span><span class="sxs-lookup"><span data-stu-id="953c4-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="953c4-107">in Valore dell'enumerazione [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) che indica il tipo di identità di un assembly.</span><span class="sxs-lookup"><span data-stu-id="953c4-107">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="953c4-108">Fornito per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="953c4-108">Provided for future extensibility.</span></span> <span data-ttu-id="953c4-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore supportato dalla versione di Common Language Runtime (CLR) 2,0.</span><span class="sxs-lookup"><span data-stu-id="953c4-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="953c4-110">out Buffer contenente i dati di identità dell'assembly opaco.</span><span class="sxs-lookup"><span data-stu-id="953c4-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="953c4-111">[in, out] Puntatore alla dimensione di `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="953c4-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="953c4-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="953c4-112">Return Value</span></span>  
  
|<span data-ttu-id="953c4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="953c4-113">HRESULT</span></span>|<span data-ttu-id="953c4-114">Description</span><span class="sxs-lookup"><span data-stu-id="953c4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="953c4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="953c4-115">S_OK</span></span>|<span data-ttu-id="953c4-116">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="953c4-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="953c4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="953c4-117">E_INVALIDARG</span></span>|<span data-ttu-id="953c4-118">L'oggetto specificato `pwzFilePath` è null.</span><span class="sxs-lookup"><span data-stu-id="953c4-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="953c4-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="953c4-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="953c4-120">La dimensione di `pwzBuffer` è troppo piccola.</span><span class="sxs-lookup"><span data-stu-id="953c4-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="953c4-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="953c4-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="953c4-122">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="953c4-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="953c4-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="953c4-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="953c4-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="953c4-124">The call timed out.</span></span>|  
|<span data-ttu-id="953c4-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="953c4-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="953c4-126">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="953c4-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="953c4-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="953c4-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="953c4-128">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="953c4-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="953c4-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="953c4-129">E_FAIL</span></span>|<span data-ttu-id="953c4-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="953c4-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="953c4-131">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="953c4-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="953c4-132">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="953c4-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="953c4-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="953c4-133">Remarks</span></span>  
 <span data-ttu-id="953c4-134">`GetBindingIdentityFromFile`viene in genere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="953c4-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="953c4-135">La prima chiamata fornisce un valore null per `pwzBuffer` e il metodo restituisce le dimensioni appropriate in `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="953c4-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="953c4-136">La seconda chiamata fornisce un buffer allocato in modo appropriato e il metodo restituisce con i dati del buffer effettivi al completamento.</span><span class="sxs-lookup"><span data-stu-id="953c4-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953c4-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="953c4-137">Requirements</span></span>  
 <span data-ttu-id="953c4-138">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="953c4-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953c4-139">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="953c4-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="953c4-140">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="953c4-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="953c4-141">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953c4-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953c4-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="953c4-142">See also</span></span>

- [<span data-ttu-id="953c4-143">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="953c4-143">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="953c4-144">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="953c4-144">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="953c4-145">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="953c4-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
