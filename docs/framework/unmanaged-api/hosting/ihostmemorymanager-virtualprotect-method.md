---
title: Metodo IHostMemoryManager::VirtualProtect
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62aa6b1d9be86a9b60abf894d67555f706e6a8ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139906"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="6a371-102">Metodo IHostMemoryManager::VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="6a371-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="6a371-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6a371-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="6a371-104">L'implementazione di Win32 di `VirtualProtect` cambia la protezione in un'area delle pagine eseguito il commit nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="6a371-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a371-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a371-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a371-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a371-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="6a371-107">[in] Un puntatore all'indirizzo di base per la memoria virtuale cui attributi di protezione devono essere modificato.</span><span class="sxs-lookup"><span data-stu-id="6a371-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="6a371-108">[in] Le dimensioni, in byte, dell'area di pagine di memoria da modificare.</span><span class="sxs-lookup"><span data-stu-id="6a371-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="6a371-109">[in] Tipo di protezione della memoria da applicare.</span><span class="sxs-lookup"><span data-stu-id="6a371-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="6a371-110">[out] Puntatore al valore di protezione della memoria precedente.</span><span class="sxs-lookup"><span data-stu-id="6a371-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a371-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6a371-111">Return Value</span></span>  
  
|<span data-ttu-id="6a371-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a371-112">HRESULT</span></span>|<span data-ttu-id="6a371-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a371-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a371-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a371-114">S_OK</span></span>|`VirtualProtect` <span data-ttu-id="6a371-115">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6a371-115">returned successfully.</span></span>|  
|<span data-ttu-id="6a371-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a371-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a371-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a371-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6a371-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a371-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6a371-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a371-119">The call timed out.</span></span>|  
|<span data-ttu-id="6a371-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6a371-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6a371-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6a371-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6a371-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6a371-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6a371-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6a371-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6a371-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a371-124">E_FAIL</span></span>|<span data-ttu-id="6a371-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6a371-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6a371-126">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6a371-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6a371-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6a371-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a371-128">Note</span><span class="sxs-lookup"><span data-stu-id="6a371-128">Remarks</span></span>  
 <span data-ttu-id="6a371-129">Questa implementazione di `VirtualProtect` restituisce un valore HRESULT, mentre l'implementazione di Win32 restituisce un valore diverso da zero per indicare l'esito positivo e un valore zero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="6a371-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="6a371-130">Per altre informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="6a371-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a371-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a371-131">Requirements</span></span>  
 <span data-ttu-id="6a371-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a371-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a371-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a371-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a371-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6a371-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6a371-135">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6a371-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a371-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a371-136">See also</span></span>

- [<span data-ttu-id="6a371-137">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="6a371-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
