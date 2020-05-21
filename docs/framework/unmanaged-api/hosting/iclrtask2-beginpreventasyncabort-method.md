---
title: Metodo ICLRTask2::BeginPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 0da18c6850f393808d05dff8b1f19ac12b05bb86
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762890"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="28ff7-102">Metodo ICLRTask2::BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="28ff7-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="28ff7-103">Ritarda la creazione di nuove richieste di interruzione del thread dal risultato di interruzioni di thread sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ff7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28ff7-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="28ff7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28ff7-105">Return Value</span></span>  
 <span data-ttu-id="28ff7-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="28ff7-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="28ff7-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28ff7-107">HRESULT</span></span>|<span data-ttu-id="28ff7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28ff7-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28ff7-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="28ff7-109">S_OK</span></span>|<span data-ttu-id="28ff7-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="28ff7-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="28ff7-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="28ff7-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ff7-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="28ff7-113">Remarks</span></span>  
 <span data-ttu-id="28ff7-114">La chiamata a questo metodo consente di incrementare di uno il contatore Delay-thread-Abort per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="28ff7-115">Le chiamate a `BeginPreventAsyncAbort` e [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) possono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="28ff7-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="28ff7-116">Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.</span><span class="sxs-lookup"><span data-stu-id="28ff7-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="28ff7-117">Se questa chiamata non è associata a una chiamata al `EndPreventAsyncAbort` metodo, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="28ff7-118">Il ritardo non viene rispettato per un thread che si interrompe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="28ff7-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="28ff7-119">La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="28ff7-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="28ff7-120">Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="28ff7-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="28ff7-121">Ad esempio, `EndPreventAsyncAbort` la chiamata a senza prima chiamata `BeginPreventAsyncAbort` potrebbe impostare il contatore su zero quando la macchina virtuale lo ha incrementato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="28ff7-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="28ff7-122">Analogamente, il contatore interno non viene controllato per l'overflow.</span><span class="sxs-lookup"><span data-stu-id="28ff7-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="28ff7-123">Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.</span><span class="sxs-lookup"><span data-stu-id="28ff7-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ff7-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28ff7-124">Requirements</span></span>  
 <span data-ttu-id="28ff7-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ff7-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ff7-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="28ff7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28ff7-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="28ff7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28ff7-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ff7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ff7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28ff7-129">See also</span></span>

- [<span data-ttu-id="28ff7-130">Metodo EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="28ff7-130">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="28ff7-131">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="28ff7-131">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="28ff7-132">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="28ff7-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="28ff7-133">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="28ff7-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="28ff7-134">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="28ff7-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="28ff7-135">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="28ff7-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
