---
title: Metodo IHostIoCompletionManager::GetHostOverlappedSize
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f21e25c077ae6ca837a41d3e2227d12dd517d95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555505"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="c4abb-102">Metodo IHostIoCompletionManager::GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="c4abb-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="c4abb-103">Ottiene le dimensioni dei dati personalizzati che nelle intenzioni di host da aggiungere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="c4abb-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4abb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4abb-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4abb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4abb-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="c4abb-106">[out] Un puntatore al numero di byte che common language runtime (CLR) è consigliabile allocare oltre alla dimensione di Win32 `OVERLAPPED` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4abb-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4abb-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c4abb-107">Return Value</span></span>  
  
|<span data-ttu-id="c4abb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4abb-108">HRESULT</span></span>|<span data-ttu-id="c4abb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4abb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4abb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4abb-110">S_OK</span></span>|<span data-ttu-id="c4abb-111">`GetHostOverlappedSize` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c4abb-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="c4abb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4abb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4abb-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c4abb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4abb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4abb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4abb-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c4abb-115">The call timed out.</span></span>|  
|<span data-ttu-id="c4abb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4abb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4abb-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="c4abb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4abb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4abb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4abb-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c4abb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4abb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4abb-120">E_FAIL</span></span>|<span data-ttu-id="c4abb-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c4abb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4abb-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c4abb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4abb-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c4abb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4abb-124">Note</span><span class="sxs-lookup"><span data-stu-id="c4abb-124">Remarks</span></span>  
 <span data-ttu-id="c4abb-125">Tutte le chiamate dei / o asincrone alle API della piattaforma Windows richiedere Win32 `OVERLAPPED` oggetto, che fornisce informazioni quali la posizione del puntatore di file.</span><span class="sxs-lookup"><span data-stu-id="c4abb-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="c4abb-126">Per mantenere lo stato, le applicazioni che effettuano chiamate dei / o asincrone in genere aggiungono dati personalizzati alla struttura.</span><span class="sxs-lookup"><span data-stu-id="c4abb-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="c4abb-127">`GetHostOverlappedSize` e [InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) offrono l'opportunità per l'host da includere tali dati.</span><span class="sxs-lookup"><span data-stu-id="c4abb-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="c4abb-128">CLR chiama il `GetHostOverlappedSize` metodo per determinare le dimensioni dei dati personalizzati che l'host da aggiungere al `OVERLAPPED` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c4abb-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4abb-129">`GetHostOverlappedSize` viene chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="c4abb-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="c4abb-130">Dati personalizzati dell'host devono avere le stesse dimensioni per ogni richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="c4abb-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4abb-131">Le dimensioni dei `OVERLAPPED` oggetto stesso non è incluso nel valore di `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="c4abb-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="c4abb-132">Per altre informazioni sul `OVERLAPPED` struttura, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="c4abb-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4abb-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4abb-133">Requirements</span></span>  
 <span data-ttu-id="c4abb-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4abb-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4abb-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4abb-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4abb-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c4abb-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4abb-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4abb-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4abb-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4abb-138">See also</span></span>
- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="c4abb-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c4abb-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c4abb-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c4abb-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
