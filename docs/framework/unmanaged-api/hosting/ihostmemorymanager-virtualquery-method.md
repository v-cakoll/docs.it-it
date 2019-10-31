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
ms.openlocfilehash: 00ec0b92a9f7151ee9b831c85548c4f61d87af68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192026"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="c5913-102">Metodo IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="c5913-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="c5913-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c5913-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="c5913-104">L'implementazione Win32 di `VirtualQuery` recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="c5913-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5913-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5913-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5913-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5913-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="c5913-107">in Puntatore all'indirizzo nella memoria virtuale su cui eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="c5913-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="c5913-108">out Puntatore a una struttura che contiene informazioni sull'area di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="c5913-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c5913-109">in Dimensione, in byte, del buffer a cui punta il `lpBuffer`.</span><span class="sxs-lookup"><span data-stu-id="c5913-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="c5913-110">out Puntatore al numero di byte restituiti dal buffer delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="c5913-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5913-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c5913-111">Return Value</span></span>  
  
|<span data-ttu-id="c5913-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5913-112">HRESULT</span></span>|<span data-ttu-id="c5913-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5913-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5913-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5913-114">S_OK</span></span>|<span data-ttu-id="c5913-115">`VirtualQuery` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c5913-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="c5913-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5913-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5913-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c5913-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5913-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5913-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5913-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5913-119">The call timed out.</span></span>|  
|<span data-ttu-id="c5913-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5913-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5913-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c5913-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5913-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5913-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5913-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c5913-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5913-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5913-124">E_FAIL</span></span>|<span data-ttu-id="c5913-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c5913-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5913-126">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c5913-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5913-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5913-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5913-128">Note</span><span class="sxs-lookup"><span data-stu-id="c5913-128">Remarks</span></span>  
 <span data-ttu-id="c5913-129">`VirtualQuery` fornisce informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="c5913-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="c5913-130">Questa implementazione imposta il valore del parametro `pResult` sul numero di byte restituiti nel buffer delle informazioni e restituisce un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c5913-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="c5913-131">Nella funzione Win32 `VirtualQuery` il valore restituito corrisponde alla dimensione del buffer.</span><span class="sxs-lookup"><span data-stu-id="c5913-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="c5913-132">Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="c5913-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c5913-133">L'implementazione del sistema operativo di `VirtualQuery` non comporta un deadlock e può essere eseguita fino al completamento con thread casuali sospesi nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="c5913-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="c5913-134">Prestare molta attenzione quando si implementa una versione ospitata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="c5913-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5913-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5913-135">Requirements</span></span>  
 <span data-ttu-id="c5913-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5913-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5913-137">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c5913-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5913-138">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5913-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5913-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5913-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5913-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5913-140">See also</span></span>

- [<span data-ttu-id="c5913-141">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c5913-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
