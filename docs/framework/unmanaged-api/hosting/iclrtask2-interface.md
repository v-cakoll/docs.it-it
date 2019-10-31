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
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124529"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="0ac5d-102">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="0ac5d-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="0ac5d-103">Fornisce tutte le funzionalità dell'interfaccia [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) ; fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ac5d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0ac5d-104">Methods</span></span>  
  
|<span data-ttu-id="0ac5d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0ac5d-105">Method</span></span>|<span data-ttu-id="0ac5d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ac5d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ac5d-107">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="0ac5d-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="0ac5d-108">Ritarda le nuove richieste di interruzione del thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="0ac5d-109">Metodo EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="0ac5d-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="0ac5d-110">Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ac5d-111">Note</span><span class="sxs-lookup"><span data-stu-id="0ac5d-111">Remarks</span></span>  
 <span data-ttu-id="0ac5d-112">L'interfaccia `ICLRTask2` eredita l'interfaccia `ICLRTask` e aggiunge metodi che consentono all'host di ritardare le interruzioni dei thread, per proteggere un'area di codice che non deve avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="0ac5d-113">La chiamata di `BeginPreventAsyncAbort` incrementa il contatore Delay-thread-Abort per il thread corrente e la chiamata `EndPreventAsyncAbort` la decrementa.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="0ac5d-114">Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="0ac5d-115">Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="0ac5d-116">Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="0ac5d-117">Il ritardo non viene rispettato per un thread che si interrompe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="0ac5d-118">La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="0ac5d-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="0ac5d-119">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="0ac5d-120">Ad esempio, la chiamata di `EndPreventAsyncAbort` senza chiamare prima `BeginPreventAsyncAbort` può impostare il contatore su zero quando la VM lo ha incrementato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="0ac5d-121">Analogamente, il contatore interno non viene controllato per l'overflow.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="0ac5d-122">Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.</span><span class="sxs-lookup"><span data-stu-id="0ac5d-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="0ac5d-123">Per informazioni sui membri ereditati da `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere l'interfaccia [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0ac5d-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac5d-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ac5d-124">Requirements</span></span>  
 <span data-ttu-id="0ac5d-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ac5d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac5d-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0ac5d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ac5d-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ac5d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ac5d-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ac5d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac5d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ac5d-129">See also</span></span>

- [<span data-ttu-id="0ac5d-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0ac5d-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0ac5d-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0ac5d-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0ac5d-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="0ac5d-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0ac5d-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0ac5d-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="0ac5d-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0ac5d-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
