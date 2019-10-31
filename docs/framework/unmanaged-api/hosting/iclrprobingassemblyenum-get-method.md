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
ms.openlocfilehash: 2ff1f9428a92d091a51a4cca12d69d98da0ecba2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120528"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="bac83-102">Metodo ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="bac83-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="bac83-103">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="bac83-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac83-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bac83-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac83-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bac83-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="bac83-106">in Indice in base zero dell'identità dell'assembly da restituire.</span><span class="sxs-lookup"><span data-stu-id="bac83-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="bac83-107">out Buffer contenente i dati di identità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bac83-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="bac83-108">[in, out] Dimensioni del buffer `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="bac83-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bac83-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bac83-109">Return Value</span></span>  
  
|<span data-ttu-id="bac83-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bac83-110">HRESULT</span></span>|<span data-ttu-id="bac83-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bac83-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bac83-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bac83-112">S_OK</span></span>|<span data-ttu-id="bac83-113">`Get` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bac83-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="bac83-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bac83-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bac83-115">il `pwzBuffer` è troppo piccolo.</span><span class="sxs-lookup"><span data-stu-id="bac83-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="bac83-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="bac83-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="bac83-117">L'enumerazione non contiene altri elementi.</span><span class="sxs-lookup"><span data-stu-id="bac83-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="bac83-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bac83-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bac83-119">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bac83-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bac83-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bac83-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bac83-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bac83-121">The call timed out.</span></span>|  
|<span data-ttu-id="bac83-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bac83-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bac83-123">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="bac83-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bac83-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bac83-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bac83-125">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bac83-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bac83-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bac83-126">E_FAIL</span></span>|<span data-ttu-id="bac83-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bac83-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bac83-128">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bac83-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bac83-129">Le chiamate successive a tutti i metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bac83-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bac83-130">Note</span><span class="sxs-lookup"><span data-stu-id="bac83-130">Remarks</span></span>  
 <span data-ttu-id="bac83-131">L'identità in corrispondenza dell'indice 0 è l'identità specifica dell'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="bac83-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="bac83-132">L'identità in corrispondenza dell'indice 1 è l'assembly indipendente dall'architettura per Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="bac83-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="bac83-133">L'identità in corrispondenza dell'indice 2 non contiene informazioni sull'architettura.</span><span class="sxs-lookup"><span data-stu-id="bac83-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="bac83-134">`Get` viene in genere chiamato due volte.</span><span class="sxs-lookup"><span data-stu-id="bac83-134">`Get` is typically called twice.</span></span> <span data-ttu-id="bac83-135">La prima chiamata fornisce un valore null per `pwzBuffer`e imposta `pcchBufferSize` sulle dimensioni appropriate per `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="bac83-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="bac83-136">La seconda chiamata fornisce un `pwzBuffer`di dimensioni appropriate e contiene i dati di identità dell'assembly canonico al termine dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bac83-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac83-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bac83-137">Requirements</span></span>  
 <span data-ttu-id="bac83-138">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bac83-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac83-139">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bac83-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bac83-140">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bac83-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bac83-141">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac83-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac83-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bac83-142">See also</span></span>

- [<span data-ttu-id="bac83-143">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="bac83-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="bac83-144">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="bac83-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
