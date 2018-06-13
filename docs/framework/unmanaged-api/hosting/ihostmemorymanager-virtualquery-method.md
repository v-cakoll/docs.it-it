---
title: Metodo IHostMemoryManager::VirtualQuery
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68a9d6ad7470ffaf1143a4a8e3134f20edb9e3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439218"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="727c1-102">Metodo IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="727c1-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="727c1-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="727c1-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="727c1-104">L'implementazione Win32 di `VirtualQuery` recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="727c1-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="727c1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="727c1-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="727c1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="727c1-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="727c1-107">[in] Un puntatore all'indirizzo nella memoria virtuale per eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="727c1-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="727c1-108">[out] Puntatore a una struttura che contiene informazioni sull'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="727c1-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="727c1-109">[in] Le dimensioni, in byte, del buffer che `lpBuffer` punta a.</span><span class="sxs-lookup"><span data-stu-id="727c1-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="727c1-110">[out] Puntatore al numero di byte restituiti dal buffer delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="727c1-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="727c1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="727c1-111">Return Value</span></span>  
  
|<span data-ttu-id="727c1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="727c1-112">HRESULT</span></span>|<span data-ttu-id="727c1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="727c1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="727c1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="727c1-114">S_OK</span></span>|<span data-ttu-id="727c1-115">`VirtualQuery` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="727c1-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="727c1-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="727c1-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="727c1-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="727c1-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="727c1-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="727c1-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="727c1-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="727c1-119">The call timed out.</span></span>|  
|<span data-ttu-id="727c1-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="727c1-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="727c1-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="727c1-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="727c1-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="727c1-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="727c1-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="727c1-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="727c1-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="727c1-124">E_FAIL</span></span>|<span data-ttu-id="727c1-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="727c1-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="727c1-126">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="727c1-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="727c1-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="727c1-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="727c1-128">Note</span><span class="sxs-lookup"><span data-stu-id="727c1-128">Remarks</span></span>  
 <span data-ttu-id="727c1-129">`VirtualQuery` fornisce informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="727c1-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="727c1-130">Questa implementazione imposta il valore di `pResult` parametro per il numero di byte restituiti nel buffer di informazioni e restituisce un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="727c1-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="727c1-131">In Win32 `VirtualQuery` funzione, il valore restituito è la dimensione del buffer.</span><span class="sxs-lookup"><span data-stu-id="727c1-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="727c1-132">Per ulteriori informazioni, vedere la documentazione di piattaforma di Windows.</span><span class="sxs-lookup"><span data-stu-id="727c1-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="727c1-133">Implementazione del sistema operativo di `VirtualQuery` è soggetta a deadlock e possono eseguire al completamento con thread casuali sospesi nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="727c1-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="727c1-134">Quando si implementa una versione ospitata di questo metodo, usare estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="727c1-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="727c1-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="727c1-135">Requirements</span></span>  
 <span data-ttu-id="727c1-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="727c1-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="727c1-137">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="727c1-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="727c1-138">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="727c1-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="727c1-139">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="727c1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727c1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="727c1-140">See Also</span></span>  
 [<span data-ttu-id="727c1-141">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="727c1-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
