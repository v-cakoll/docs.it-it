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
ms.openlocfilehash: cf257ab86d27946c861c89dff5e6f09a42013e58
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804705"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="0280a-102">Metodo IHostIoCompletionManager::InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="0280a-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="0280a-103">Fornisce all'host la possibilità di inizializzare i dati personalizzati da accodare a una `OVERLAPPED` struttura Win32 utilizzata per le richieste di I/O asincrone.</span><span class="sxs-lookup"><span data-stu-id="0280a-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0280a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0280a-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0280a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0280a-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="0280a-106">in Puntatore alla `OVERLAPPED` struttura Win32 da includere con la richiesta di i/O.</span><span class="sxs-lookup"><span data-stu-id="0280a-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0280a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0280a-107">Return Value</span></span>  
  
|<span data-ttu-id="0280a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0280a-108">HRESULT</span></span>|<span data-ttu-id="0280a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0280a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0280a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0280a-110">S_OK</span></span>|<span data-ttu-id="0280a-111">`InitializeHostOverlapped`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0280a-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="0280a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0280a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0280a-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0280a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0280a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0280a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0280a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0280a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0280a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0280a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0280a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0280a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0280a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0280a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0280a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0280a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0280a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0280a-120">E_FAIL</span></span>|<span data-ttu-id="0280a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0280a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0280a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0280a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0280a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0280a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0280a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0280a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0280a-125">Memoria insufficiente per l'allocazione della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="0280a-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0280a-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0280a-126">Remarks</span></span>  
 <span data-ttu-id="0280a-127">Le funzioni della piattaforma Windows utilizzano la `OVERLAPPED` struttura per archiviare lo stato delle richieste di I/O asincrone.</span><span class="sxs-lookup"><span data-stu-id="0280a-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="0280a-128">CLR chiama il `InitializeHostOverlapped` metodo per concedere all'host la possibilità di accodare dati personalizzati a un' `OVERLAPPED` istanza di.</span><span class="sxs-lookup"><span data-stu-id="0280a-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0280a-129">Per ottenere l'inizio del blocco di dati personalizzato, gli host devono impostare l'offset sulle dimensioni della `OVERLAPPED` struttura ( `sizeof(OVERLAPPED)` ).</span><span class="sxs-lookup"><span data-stu-id="0280a-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="0280a-130">Un valore restituito di E_OUTOFMEMORY indica che l'host non è stato in grado di inizializzare i dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0280a-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="0280a-131">In questo caso, CLR segnala un errore e non riesce a chiamare.</span><span class="sxs-lookup"><span data-stu-id="0280a-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0280a-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0280a-132">Requirements</span></span>  
 <span data-ttu-id="0280a-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0280a-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0280a-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0280a-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0280a-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0280a-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0280a-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0280a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0280a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0280a-137">See also</span></span>

- [<span data-ttu-id="0280a-138">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0280a-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0280a-139">Metodo GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="0280a-139">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="0280a-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0280a-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
