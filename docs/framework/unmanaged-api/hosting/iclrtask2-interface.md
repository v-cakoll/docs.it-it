---
title: Interfaccia ICLRTask2
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518248651de6d8afdf25692c5f48da52b11eb0f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763399"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="78634-102">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="78634-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="78634-103">Fornisce tutte le funzionalità dei [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia; inoltre, fornisce metodi che consentono le interruzioni dei thread per essere ritardato sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="78634-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78634-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="78634-104">Methods</span></span>  
  
|<span data-ttu-id="78634-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="78634-105">Method</span></span>|<span data-ttu-id="78634-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78634-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78634-107">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="78634-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="78634-108">Ritardi nuove richieste di interruzione sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="78634-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="78634-109">Metodo EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="78634-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="78634-110">Consente di nuovo o in sospeso alle richieste di interruzione di thread ottengano in thread viene interrotto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="78634-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78634-111">Note</span><span class="sxs-lookup"><span data-stu-id="78634-111">Remarks</span></span>  
 <span data-ttu-id="78634-112">Il `ICLRTask2` interfaccia eredita il `ICLRTask` l'interfaccia e aggiunge i metodi che consentono all'host ritardare le interruzioni di thread, per proteggere un'area di codice che non deve avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="78634-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="78634-113">La chiamata `BeginPreventAsyncAbort` incrementa il contatore di ritardo di interruzione per il thread corrente e chiamare il metodo `EndPreventAsyncAbort` decrementa è.</span><span class="sxs-lookup"><span data-stu-id="78634-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="78634-114">Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="78634-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="78634-115">Ritardo fino a quando il contatore è maggiore di zero, interruzioni di thread per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="78634-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="78634-116">Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato nel quale thread interruzioni non possono essere recapitate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="78634-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="78634-117">Il ritardo non viene applicato per un thread che interrompe se stesso.</span><span class="sxs-lookup"><span data-stu-id="78634-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="78634-118">La funzionalità che viene esposto da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="78634-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="78634-119">Un uso improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="78634-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="78634-120">Ad esempio, chiamando `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` è stato possibile impostare il contatore a zero quando la macchina virtuale in precedenza ha incrementato in.</span><span class="sxs-lookup"><span data-stu-id="78634-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="78634-121">Analogamente, il contatore interno non viene controllato dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="78634-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="78634-122">Se l'utilizzo supera il limite di integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.</span><span class="sxs-lookup"><span data-stu-id="78634-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="78634-123">Per informazioni sui membri ereditata dal `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="78634-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78634-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78634-124">Requirements</span></span>  
 <span data-ttu-id="78634-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78634-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78634-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78634-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78634-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="78634-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78634-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78634-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78634-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78634-129">See also</span></span>

- [<span data-ttu-id="78634-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="78634-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="78634-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="78634-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="78634-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="78634-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="78634-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="78634-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="78634-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="78634-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
