---
title: Metodo ICLRProbingAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f5ddd352d027365e02366e9aa779053da3bdc2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434804"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="13448-102">Metodo ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="13448-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="13448-103">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="13448-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13448-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13448-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13448-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13448-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="13448-106">[in] Indice in base zero dell'identità dell'assembly da restituire.</span><span class="sxs-lookup"><span data-stu-id="13448-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="13448-107">[out] Un buffer contenente i dati di identità di assembly.</span><span class="sxs-lookup"><span data-stu-id="13448-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="13448-108">[in, out] Le dimensioni del `pwzBuffer` buffer.</span><span class="sxs-lookup"><span data-stu-id="13448-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13448-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="13448-109">Return Value</span></span>  
  
|<span data-ttu-id="13448-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13448-110">HRESULT</span></span>|<span data-ttu-id="13448-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13448-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13448-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="13448-112">S_OK</span></span>|<span data-ttu-id="13448-113">`Get` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="13448-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="13448-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="13448-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="13448-115">`pwzBuffer` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="13448-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="13448-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="13448-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="13448-117">L'enumerazione non contiene più elementi.</span><span class="sxs-lookup"><span data-stu-id="13448-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="13448-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13448-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13448-119">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="13448-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13448-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13448-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13448-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="13448-121">The call timed out.</span></span>|  
|<span data-ttu-id="13448-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13448-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13448-123">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="13448-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13448-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13448-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13448-125">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="13448-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13448-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13448-126">E_FAIL</span></span>|<span data-ttu-id="13448-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="13448-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13448-128">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="13448-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13448-129">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="13448-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13448-130">Note</span><span class="sxs-lookup"><span data-stu-id="13448-130">Remarks</span></span>  
 <span data-ttu-id="13448-131">L'identità in corrispondenza dell'indice 0 è l'identità specifica per l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="13448-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="13448-132">L'identità in corrispondenza dell'indice 1 è l'assembly di architettura neutra per Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="13448-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="13448-133">L'identità in corrispondenza dell'indice 2 non contiene alcuna informazione di architettura.</span><span class="sxs-lookup"><span data-stu-id="13448-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="13448-134">`Get` viene in genere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="13448-134">`Get` is typically called twice.</span></span> <span data-ttu-id="13448-135">La prima chiamata fornisce un valore null per `pwzBuffer`e imposta `pcchBufferSize` per le dimensioni appropriate per `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="13448-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="13448-136">La seconda chiamata viene fornito un dimensionati `pwzBuffer`e contiene i dati di identità assembly canonica dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="13448-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13448-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13448-137">Requirements</span></span>  
 <span data-ttu-id="13448-138">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13448-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13448-139">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="13448-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13448-140">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="13448-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13448-141">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13448-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13448-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13448-142">See Also</span></span>  
 [<span data-ttu-id="13448-143">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="13448-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [<span data-ttu-id="13448-144">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="13448-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
