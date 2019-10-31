---
title: Metodo ICLRTask2::EndPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 8ae66e0bf96138e5bc2f33e4c14ad86e7dabc6b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124544"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="fc976-102">Metodo ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="fc976-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="fc976-103">Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="fc976-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc976-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc976-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fc976-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc976-105">Return Value</span></span>  
 <span data-ttu-id="fc976-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="fc976-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fc976-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc976-107">HRESULT</span></span>|<span data-ttu-id="fc976-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc976-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc976-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc976-109">S_OK</span></span>|<span data-ttu-id="fc976-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fc976-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="fc976-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="fc976-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="fc976-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="fc976-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc976-113">Note</span><span class="sxs-lookup"><span data-stu-id="fc976-113">Remarks</span></span>  
 <span data-ttu-id="fc976-114">La chiamata a questo metodo decrementa di uno il contatore Delay-thread-Abort per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="fc976-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="fc976-115">Le chiamate a [ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) e `EndPreventAsyncAbort` possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="fc976-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="fc976-116">Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.</span><span class="sxs-lookup"><span data-stu-id="fc976-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="fc976-117">La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="fc976-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="fc976-118">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="fc976-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="fc976-119">Ad esempio, la chiamata di `EndPreventAsyncAbort` senza chiamare prima `BeginPreventAsyncAbort` può impostare il contatore su zero quando la VM lo ha incrementato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fc976-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="fc976-120">Analogamente, il contatore interno non viene controllato per l'overflow.</span><span class="sxs-lookup"><span data-stu-id="fc976-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="fc976-121">Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.</span><span class="sxs-lookup"><span data-stu-id="fc976-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc976-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc976-122">Requirements</span></span>  
 <span data-ttu-id="fc976-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc976-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc976-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc976-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc976-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc976-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc976-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc976-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc976-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc976-127">See also</span></span>

- [<span data-ttu-id="fc976-128">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="fc976-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="fc976-129">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="fc976-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="fc976-130">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fc976-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fc976-131">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="fc976-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fc976-132">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fc976-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="fc976-133">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="fc976-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
