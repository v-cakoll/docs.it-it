---
title: Metodo ICLRTask2::EndPreventAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.EndPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c76a75004b4593e8e93aa4dd999c85c0fb7cf38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="9bfc5-102">Metodo ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="9bfc5-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="9bfc5-103">Consente di nuovo o richieste di interruzione del thread restituiscono di thread in sospeso interrompe il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bfc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bfc5-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9bfc5-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9bfc5-105">Return Value</span></span>  
 <span data-ttu-id="9bfc5-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9bfc5-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9bfc5-107">HRESULT</span></span>|<span data-ttu-id="9bfc5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bfc5-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9bfc5-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bfc5-109">S_OK</span></span>|<span data-ttu-id="9bfc5-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="9bfc5-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="9bfc5-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="9bfc5-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bfc5-113">Note</span><span class="sxs-lookup"><span data-stu-id="9bfc5-113">Remarks</span></span>  
 <span data-ttu-id="9bfc5-114">Chiamata di questo contatore decrementa il ritardo di interruzione di metodo per il thread corrente da uno.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="9bfc5-115">Le chiamate a [Iclrtask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) e `EndPreventAsyncAbort` possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="9bfc5-116">Fino a quando il contatore è maggiore di zero, vengono posticipate interruzioni del thread per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="9bfc5-117">La funzionalità esposta da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="9bfc5-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="9bfc5-118">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="9bfc5-119">Ad esempio, la chiamata `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` Impossibile impostare il contatore a zero quando la macchina virtuale ha incrementato in precedenza in.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="9bfc5-120">Analogamente, il contatore interno non viene verificato per overflow.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="9bfc5-121">Se superato questo limite integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.</span><span class="sxs-lookup"><span data-stu-id="9bfc5-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bfc5-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bfc5-122">Requirements</span></span>  
 <span data-ttu-id="9bfc5-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bfc5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bfc5-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9bfc5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9bfc5-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9bfc5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bfc5-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bfc5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfc5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bfc5-127">See Also</span></span>  
 [<span data-ttu-id="9bfc5-128">BeginPreventAsyncAbort (metodo)</span><span class="sxs-lookup"><span data-stu-id="9bfc5-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="9bfc5-129">ICLRTask2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9bfc5-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="9bfc5-130">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9bfc5-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9bfc5-131">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9bfc5-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9bfc5-132">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9bfc5-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="9bfc5-133">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9bfc5-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
