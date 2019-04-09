---
title: Metodo IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157670"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="fa15b-102">Metodo IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="fa15b-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="fa15b-103">Fornisce l'host con un'opportunità per inizializzare dati personalizzati da aggiungere a un Win32 `OVERLAPPED` struttura utilizzata per le richieste dei / o asincrone.</span><span class="sxs-lookup"><span data-stu-id="fa15b-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa15b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa15b-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa15b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa15b-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="fa15b-106">[in] Un puntatore a Win32 `OVERLAPPED` struttura deve essere incluso con la richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="fa15b-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa15b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa15b-107">Return Value</span></span>  
  
|<span data-ttu-id="fa15b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa15b-108">HRESULT</span></span>|<span data-ttu-id="fa15b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa15b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa15b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa15b-110">S_OK</span></span>|`InitializeHostOverlapped` <span data-ttu-id="fa15b-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fa15b-111">returned successfully.</span></span>|  
|<span data-ttu-id="fa15b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa15b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa15b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa15b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa15b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa15b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa15b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa15b-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa15b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa15b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa15b-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="fa15b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa15b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa15b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa15b-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fa15b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa15b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa15b-120">E_FAIL</span></span>|<span data-ttu-id="fa15b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fa15b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa15b-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fa15b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa15b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fa15b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fa15b-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fa15b-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fa15b-125">Memoria insufficiente era disponibile da allocare alla risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="fa15b-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa15b-126">Note</span><span class="sxs-lookup"><span data-stu-id="fa15b-126">Remarks</span></span>  
 <span data-ttu-id="fa15b-127">La piattaforma di Windows funzioni utilizzano il `OVERLAPPED` struttura per archiviare lo stato delle richieste dei / o asincrone.</span><span class="sxs-lookup"><span data-stu-id="fa15b-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="fa15b-128">CLR chiama il `InitializeHostOverlapped` metodo per consentire all'host la possibilità di accodare i dati personalizzati a un `OVERLAPPED` istanza.</span><span class="sxs-lookup"><span data-stu-id="fa15b-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa15b-129">Per ottenere all'inizio del proprio blocco di dati personalizzati, gli host devono impostare l'offset alle dimensioni dei `OVERLAPPED` struttura (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="fa15b-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="fa15b-130">Un valore restituito E_OUTOFMEMORY indica che l'host non è riuscito a inizializzare i dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fa15b-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="fa15b-131">In questo caso, CLR segnala un errore e ha esito negativo della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa15b-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa15b-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa15b-132">Requirements</span></span>  
 <span data-ttu-id="fa15b-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa15b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa15b-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa15b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa15b-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fa15b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fa15b-136">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fa15b-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa15b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa15b-137">See also</span></span>

- [<span data-ttu-id="fa15b-138">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fa15b-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="fa15b-139">Metodo GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="fa15b-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="fa15b-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fa15b-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
