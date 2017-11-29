---
title: Interfaccia ICLRTask2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="95a32-102">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="95a32-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="95a32-103">Fornisce tutte le funzionalità del [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia; inoltre, fornisce metodi che consentono l'interruzione di thread per ritardare il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="95a32-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95a32-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="95a32-104">Methods</span></span>  
  
|<span data-ttu-id="95a32-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="95a32-105">Method</span></span>|<span data-ttu-id="95a32-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95a32-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95a32-107">BeginPreventAsyncAbort (metodo)</span><span class="sxs-lookup"><span data-stu-id="95a32-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="95a32-108">Ritardi nuove richieste di interruzione sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="95a32-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="95a32-109">EndPreventAsyncAbort (metodo)</span><span class="sxs-lookup"><span data-stu-id="95a32-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="95a32-110">Consente di nuovo o richieste di interruzione del thread restituiscono di thread in sospeso interrompe il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="95a32-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95a32-111">Note</span><span class="sxs-lookup"><span data-stu-id="95a32-111">Remarks</span></span>  
 <span data-ttu-id="95a32-112">Il `ICLRTask2` interfaccia eredita il `ICLRTask` l'interfaccia e aggiunge i metodi che consentono all'host di ritardo interruzioni del thread, per proteggere un'area di codice che non deve avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="95a32-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="95a32-113">La chiamata `BeginPreventAsyncAbort` incrementa il contatore di ritardo di interruzione per il thread corrente e la chiamata `EndPreventAsyncAbort` decrementa il.</span><span class="sxs-lookup"><span data-stu-id="95a32-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="95a32-114">Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="95a32-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="95a32-115">Fino a quando il contatore è maggiore di zero, vengono posticipate interruzioni del thread per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="95a32-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="95a32-116">Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono associato, è possibile raggiungere uno stato nel quale thread viene interrotta non può essere recapitato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="95a32-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="95a32-117">Il ritardo non è valido per un thread che interrompe se stesso.</span><span class="sxs-lookup"><span data-stu-id="95a32-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="95a32-118">La funzionalità esposta da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="95a32-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="95a32-119">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="95a32-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="95a32-120">Ad esempio, la chiamata `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` Impossibile impostare il contatore a zero quando la macchina virtuale ha incrementato in precedenza in.</span><span class="sxs-lookup"><span data-stu-id="95a32-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="95a32-121">Analogamente, il contatore interno non viene verificato per overflow.</span><span class="sxs-lookup"><span data-stu-id="95a32-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="95a32-122">Se superato questo limite integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.</span><span class="sxs-lookup"><span data-stu-id="95a32-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="95a32-123">Per informazioni sui membri ereditati da `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere il [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="95a32-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95a32-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95a32-124">Requirements</span></span>  
 <span data-ttu-id="95a32-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95a32-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95a32-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="95a32-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95a32-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95a32-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95a32-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95a32-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a32-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a32-129">See Also</span></span>  
 [<span data-ttu-id="95a32-130">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95a32-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="95a32-131">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95a32-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="95a32-132">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95a32-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="95a32-133">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95a32-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="95a32-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="95a32-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
