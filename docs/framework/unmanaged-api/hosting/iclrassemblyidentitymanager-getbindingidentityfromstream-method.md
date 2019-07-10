---
title: Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16cb3495bbc2fa9ead25afd5e7120774b021a37f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773553"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="876c3-102">Metodo ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="876c3-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="876c3-103">Ottiene i dati di identità di assembly canonico per l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="876c3-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="876c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="876c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="876c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="876c3-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="876c3-106">[in] Il flusso di assembly da valutare.</span><span class="sxs-lookup"><span data-stu-id="876c3-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="876c3-107">[in] Fornito per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="876c3-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="876c3-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT è l'unico valore che supporta la versione corrente di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="876c3-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="876c3-109">[out] Un buffer contenente i dati di identità di assembly opaco.</span><span class="sxs-lookup"><span data-stu-id="876c3-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="876c3-110">[in, out] Le dimensioni di `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="876c3-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="876c3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="876c3-111">Return Value</span></span>  
  
|<span data-ttu-id="876c3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="876c3-112">HRESULT</span></span>|<span data-ttu-id="876c3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="876c3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="876c3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="876c3-114">S_OK</span></span>|<span data-ttu-id="876c3-115">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="876c3-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="876c3-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="876c3-116">E_INVALIDARG</span></span>|<span data-ttu-id="876c3-117">Il parametro fornito `pStream` è null.</span><span class="sxs-lookup"><span data-stu-id="876c3-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="876c3-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="876c3-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="876c3-119">Le dimensioni di `pwzBuffer` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="876c3-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="876c3-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="876c3-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="876c3-121">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="876c3-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="876c3-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="876c3-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="876c3-123">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="876c3-123">The call timed out.</span></span>|  
|<span data-ttu-id="876c3-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="876c3-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="876c3-125">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="876c3-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="876c3-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="876c3-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="876c3-127">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="876c3-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="876c3-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="876c3-128">E_FAIL</span></span>|<span data-ttu-id="876c3-129">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="876c3-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="876c3-130">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="876c3-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="876c3-131">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="876c3-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="876c3-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="876c3-132">Requirements</span></span>  
 <span data-ttu-id="876c3-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="876c3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="876c3-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="876c3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="876c3-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="876c3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="876c3-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="876c3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876c3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="876c3-137">See also</span></span>

- [<span data-ttu-id="876c3-138">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="876c3-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="876c3-139">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="876c3-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
