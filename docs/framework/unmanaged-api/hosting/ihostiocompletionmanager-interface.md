---
title: Interfaccia IHostIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197269"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="38a25-102">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="38a25-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="38a25-103">Fornisce metodi che consentono di common language runtime (CLR) per interagire con le porte di completamento i/o fornite dall'host.</span><span class="sxs-lookup"><span data-stu-id="38a25-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38a25-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="38a25-104">Methods</span></span>  
  
|<span data-ttu-id="38a25-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="38a25-105">Method</span></span>|<span data-ttu-id="38a25-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38a25-107">Metodo bind</span><span class="sxs-lookup"><span data-stu-id="38a25-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="38a25-108">Associa un handle a una porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="38a25-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="38a25-109">Metodo CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="38a25-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="38a25-110">Chiude una porta che è stata creata tramite una chiamata precedente a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="38a25-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="38a25-111">Metodo CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="38a25-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="38a25-112">Richieste all'host di creare una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="38a25-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="38a25-113">Metodo GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="38a25-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="38a25-114">Ottiene il numero di thread di completamento i/o che non stanno elaborando le richieste.</span><span class="sxs-lookup"><span data-stu-id="38a25-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="38a25-115">Metodo GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="38a25-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="38a25-116">Ottiene le dimensioni dei dati personalizzati che nelle intenzioni di host da aggiungere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="38a25-117">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="38a25-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="38a25-118">Ottiene il numero massimo di thread che l'host può allocare per soddisfare le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="38a25-119">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="38a25-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="38a25-120">Ottiene il numero minimo di thread forniti dall'host per soddisfare le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="38a25-121">Metodo InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="38a25-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="38a25-122">Fornisce un'opportunità per inizializzare dati personalizzati relativi a una richiesta dei / o all'host.</span><span class="sxs-lookup"><span data-stu-id="38a25-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="38a25-123">Metodo SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="38a25-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="38a25-124">Fornisce l'host con un puntatore a interfaccia a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementato da CLR.</span><span class="sxs-lookup"><span data-stu-id="38a25-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="38a25-125">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="38a25-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="38a25-126">Imposta il numero massimo di thread che l'host assegnati per soddisfare le richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="38a25-127">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="38a25-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="38a25-128">Imposta il numero minimo di thread che l'host deve allocare fino al completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38a25-129">Note</span><span class="sxs-lookup"><span data-stu-id="38a25-129">Remarks</span></span>  
 <span data-ttu-id="38a25-130">`IHostIoCompletionManager` corrisponde alla `ICLRIoCompletionManager` interfaccia implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="38a25-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="38a25-131">CLR chiama i metodi del `IHostIoCompletionManager` per associare gli handle per le porte che fornisce l'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="38a25-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a25-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38a25-132">Requirements</span></span>  
 <span data-ttu-id="38a25-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38a25-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a25-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38a25-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38a25-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="38a25-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38a25-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a25-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a25-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38a25-137">See also</span></span>

- [<span data-ttu-id="38a25-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="38a25-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
