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
ms.openlocfilehash: 90675d9be71342efa903767abbf63102b40a2c35
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804683"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="08d12-102">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="08d12-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="08d12-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di interagire con le porte di completamento I/O fornite dall'host.</span><span class="sxs-lookup"><span data-stu-id="08d12-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08d12-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="08d12-104">Methods</span></span>  
  
|<span data-ttu-id="08d12-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="08d12-105">Method</span></span>|<span data-ttu-id="08d12-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08d12-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08d12-107">Metodo bind</span><span class="sxs-lookup"><span data-stu-id="08d12-107">Bind Method</span></span>](ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="08d12-108">Associa un handle a una porta di completamento di I/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="08d12-109">Metodo CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="08d12-109">CloseIoCompletionPort Method</span></span>](ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="08d12-110">Chiude una porta creata tramite una chiamata precedente a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="08d12-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="08d12-111">Metodo CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="08d12-111">CreateIoCompletionPort Method</span></span>](ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="08d12-112">Richiede che l'host crei una nuova porta di completamento di I/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="08d12-113">Metodo GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="08d12-113">GetAvailableThreads Method</span></span>](ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="08d12-114">Ottiene il numero di thread di completamento di I/O che non stanno attualmente elaborando richieste.</span><span class="sxs-lookup"><span data-stu-id="08d12-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="08d12-115">Metodo GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="08d12-115">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="08d12-116">Ottiene le dimensioni dei dati personalizzati che l'host intende accodare alle richieste di I/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="08d12-117">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="08d12-117">GetMaxThreads Method</span></span>](ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="08d12-118">Ottiene il numero massimo di thread che l'host può allocare alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="08d12-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="08d12-119">Metodo GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="08d12-119">GetMinThreads Method</span></span>](ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="08d12-120">Ottiene il numero minimo di thread fornito dall'host alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="08d12-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="08d12-121">Metodo InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="08d12-121">InitializeHostOverlapped Method</span></span>](ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="08d12-122">Fornisce all'host la possibilità di inizializzare tutti i dati personalizzati relativi a una richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="08d12-123">Metodo SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="08d12-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="08d12-124">Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="08d12-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="08d12-125">Metodo SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="08d12-125">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="08d12-126">Imposta il numero massimo di thread allocati dall'host alle richieste di I/O del servizio.</span><span class="sxs-lookup"><span data-stu-id="08d12-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="08d12-127">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="08d12-127">SetMinThreads Method</span></span>](ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="08d12-128">Imposta il numero minimo di thread che l'host deve assegnare al completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08d12-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="08d12-129">Remarks</span></span>  
 <span data-ttu-id="08d12-130">`IHostIoCompletionManager`corrisponde all' `ICLRIoCompletionManager` interfaccia implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="08d12-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="08d12-131">CLR chiama i metodi di `IHostIoCompletionManager` per associare gli handle alle porte fornite dall'host e l'host chiama i metodi di `ICLRIoCompletionManager` per segnalare il completamento delle richieste di i/O.</span><span class="sxs-lookup"><span data-stu-id="08d12-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d12-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08d12-132">Requirements</span></span>  
 <span data-ttu-id="08d12-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08d12-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d12-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="08d12-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08d12-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="08d12-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08d12-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d12-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d12-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08d12-137">See also</span></span>

- [<span data-ttu-id="08d12-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="08d12-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
