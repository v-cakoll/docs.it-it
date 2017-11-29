---
title: Interfaccia IHostIoCompletionManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager
helpviewer_keywords: IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 847d4c3aa3e3da94b4aac4679ada047577379f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="aa32e-102">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="aa32e-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="aa32e-103">Fornisce metodi che consentono a common language runtime (CLR) per interagire con le porte di completamento i/o fornite dall'host.</span><span class="sxs-lookup"><span data-stu-id="aa32e-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa32e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="aa32e-104">Methods</span></span>  
  
|<span data-ttu-id="aa32e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="aa32e-105">Method</span></span>|<span data-ttu-id="aa32e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa32e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa32e-107">Bind (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="aa32e-108">Associa un handle a una porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="aa32e-109">CloseIoCompletionPort (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="aa32e-110">Chiude una porta creata tramite una chiamata precedente a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="aa32e-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="aa32e-111">CreateIoCompletionPort (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="aa32e-112">Richieste all'host di creare una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="aa32e-113">GetAvailableThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="aa32e-114">Ottiene il numero di thread di completamento i/o che non stanno elaborando le richieste.</span><span class="sxs-lookup"><span data-stu-id="aa32e-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="aa32e-115">GetHostOverlappedSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="aa32e-116">Ottiene le dimensioni dei dati personalizzati, che l'host dovrà accodare alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="aa32e-117">GetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="aa32e-118">Ottiene il numero massimo di thread che l'host è possibile allocare per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="aa32e-119">GetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="aa32e-120">Ottiene il numero minimo di thread che l'host fornisce per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="aa32e-121">InitializeHostOverlapped (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="aa32e-122">Fornisce all'host la possibilità di inizializzare qualsiasi dato personalizzato su una richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="aa32e-123">SetCLRIoCompletionManager (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="aa32e-124">Fornisce all'host con un puntatore a interfaccia a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="aa32e-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="aa32e-125">SetMaxThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="aa32e-126">Imposta il numero massimo di thread che l'host assegnati per rispondere alle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="aa32e-127">SetMinThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="aa32e-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="aa32e-128">Imposta il numero minimo di thread che l'host deve assegnare fino al completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa32e-129">Note</span><span class="sxs-lookup"><span data-stu-id="aa32e-129">Remarks</span></span>  
 <span data-ttu-id="aa32e-130">`IHostIoCompletionManager`corrisponde alla `ICLRIoCompletionManager` interfaccia implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="aa32e-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="aa32e-131">CLR chiama i metodi di `IHostIoCompletionManager` per associare gli handle per le porte che fornisce l'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste dei / o.</span><span class="sxs-lookup"><span data-stu-id="aa32e-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa32e-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa32e-132">Requirements</span></span>  
 <span data-ttu-id="aa32e-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa32e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa32e-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="aa32e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa32e-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa32e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa32e-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa32e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa32e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa32e-137">See Also</span></span>  
 [<span data-ttu-id="aa32e-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="aa32e-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
