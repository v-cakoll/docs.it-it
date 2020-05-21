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
ms.openlocfilehash: 3ea36c56ef9ccf5886ba96191627e5283da186f7
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762853"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="6b68b-102">Metodo ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6b68b-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="6b68b-103">Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="6b68b-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b68b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b68b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6b68b-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6b68b-105">Return Value</span></span>  
 <span data-ttu-id="6b68b-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="6b68b-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6b68b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b68b-107">HRESULT</span></span>|<span data-ttu-id="6b68b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b68b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b68b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b68b-109">S_OK</span></span>|<span data-ttu-id="6b68b-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6b68b-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="6b68b-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="6b68b-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="6b68b-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="6b68b-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b68b-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6b68b-113">Remarks</span></span>  
 <span data-ttu-id="6b68b-114">La chiamata a questo metodo decrementa di uno il contatore Delay-thread-Abort per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="6b68b-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="6b68b-115">Le chiamate a [ICLRTask2:: BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) e `EndPreventAsyncAbort` possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="6b68b-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="6b68b-116">Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.</span><span class="sxs-lookup"><span data-stu-id="6b68b-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="6b68b-117">La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="6b68b-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="6b68b-118">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="6b68b-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="6b68b-119">Ad esempio, `EndPreventAsyncAbort` la chiamata a senza prima chiamata `BeginPreventAsyncAbort` potrebbe impostare il contatore su zero quando la macchina virtuale lo ha incrementato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6b68b-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="6b68b-120">Analogamente, il contatore interno non viene controllato per l'overflow.</span><span class="sxs-lookup"><span data-stu-id="6b68b-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="6b68b-121">Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.</span><span class="sxs-lookup"><span data-stu-id="6b68b-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b68b-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b68b-122">Requirements</span></span>  
 <span data-ttu-id="6b68b-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b68b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b68b-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b68b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b68b-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b68b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b68b-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b68b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b68b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b68b-127">See also</span></span>

- [<span data-ttu-id="6b68b-128">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6b68b-128">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="6b68b-129">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="6b68b-129">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="6b68b-130">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6b68b-130">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6b68b-131">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="6b68b-131">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6b68b-132">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6b68b-132">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6b68b-133">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6b68b-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
