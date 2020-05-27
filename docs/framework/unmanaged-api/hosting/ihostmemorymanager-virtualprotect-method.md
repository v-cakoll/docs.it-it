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
ms.openlocfilehash: 473a52b55f793abc76883b0a5cd5b2a04756d9f7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804365"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="8d759-102">Metodo IHostMemoryManager::VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="8d759-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="8d759-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8d759-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="8d759-104">L'implementazione Win32 di `VirtualProtect` modifica la protezione in un'area di pagine di cui è stato eseguito il commit nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d759-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d759-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d759-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d759-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d759-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="8d759-107">in Puntatore all'indirizzo di base della memoria virtuale di cui devono essere modificati gli attributi di protezione.</span><span class="sxs-lookup"><span data-stu-id="8d759-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="8d759-108">in Dimensione, in byte, dell'area delle pagine di memoria da modificare.</span><span class="sxs-lookup"><span data-stu-id="8d759-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="8d759-109">in Tipo di protezione della memoria da applicare.</span><span class="sxs-lookup"><span data-stu-id="8d759-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="8d759-110">out Puntatore al valore precedente della protezione della memoria.</span><span class="sxs-lookup"><span data-stu-id="8d759-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d759-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d759-111">Return Value</span></span>  
  
|<span data-ttu-id="8d759-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d759-112">HRESULT</span></span>|<span data-ttu-id="8d759-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d759-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d759-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d759-114">S_OK</span></span>|<span data-ttu-id="8d759-115">`VirtualProtect`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8d759-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="8d759-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d759-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d759-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d759-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d759-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d759-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d759-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d759-119">The call timed out.</span></span>|  
|<span data-ttu-id="8d759-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d759-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d759-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8d759-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d759-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d759-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d759-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8d759-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d759-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d759-124">E_FAIL</span></span>|<span data-ttu-id="8d759-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8d759-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d759-126">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8d759-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d759-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8d759-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d759-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8d759-128">Remarks</span></span>  
 <span data-ttu-id="8d759-129">Questa implementazione di `VirtualProtect` restituisce un valore HRESULT, mentre l'implementazione Win32 restituisce un valore diverso da zero per indicare l'esito positivo e un valore zero per indicare l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8d759-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="8d759-130">Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="8d759-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d759-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d759-131">Requirements</span></span>  
 <span data-ttu-id="8d759-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d759-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d759-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8d759-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d759-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d759-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d759-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d759-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d759-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d759-136">See also</span></span>

- [<span data-ttu-id="8d759-137">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="8d759-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
