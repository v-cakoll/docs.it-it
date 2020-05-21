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
ms.openlocfilehash: b067ca72e030bce24a7efde5e3488a00024e9613
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762867"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="5d1fa-102">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="5d1fa-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="5d1fa-103">Fornisce tutte le funzionalità dell'interfaccia [ICLRTask](iclrtask-interface.md) ; fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-103">Provides all the functionality of the [ICLRTask](iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d1fa-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d1fa-104">Methods</span></span>  
  
|<span data-ttu-id="5d1fa-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d1fa-105">Method</span></span>|<span data-ttu-id="5d1fa-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d1fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d1fa-107">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="5d1fa-107">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="5d1fa-108">Ritarda le nuove richieste di interruzione del thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="5d1fa-109">Metodo EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="5d1fa-109">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="5d1fa-110">Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d1fa-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5d1fa-111">Remarks</span></span>  
 <span data-ttu-id="5d1fa-112">L' `ICLRTask2` interfaccia eredita l' `ICLRTask` interfaccia e aggiunge metodi che consentono all'host di ritardare le interruzioni dei thread, per proteggere un'area di codice che non deve avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="5d1fa-113">`BeginPreventAsyncAbort`La chiamata a incrementa il contatore Delay-thread-Abort per il thread corrente e la chiamata `EndPreventAsyncAbort` viene decrementata.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="5d1fa-114">Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="5d1fa-115">Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="5d1fa-116">Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="5d1fa-117">Il ritardo non viene rispettato per un thread che si interrompe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="5d1fa-118">La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="5d1fa-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="5d1fa-119">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="5d1fa-120">Ad esempio, `EndPreventAsyncAbort` la chiamata a senza prima chiamata `BeginPreventAsyncAbort` potrebbe impostare il contatore su zero quando la macchina virtuale lo ha incrementato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="5d1fa-121">Analogamente, il contatore interno non viene controllato per l'overflow.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="5d1fa-122">Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.</span><span class="sxs-lookup"><span data-stu-id="5d1fa-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="5d1fa-123">Per informazioni sui membri ereditati da `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere l'interfaccia [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5d1fa-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d1fa-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d1fa-124">Requirements</span></span>  
 <span data-ttu-id="5d1fa-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d1fa-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d1fa-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5d1fa-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d1fa-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5d1fa-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d1fa-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d1fa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1fa-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d1fa-129">See also</span></span>

- [<span data-ttu-id="5d1fa-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5d1fa-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5d1fa-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d1fa-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5d1fa-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="5d1fa-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5d1fa-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d1fa-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="5d1fa-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5d1fa-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
