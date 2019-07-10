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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36947eb33460fe3f15cf4ade1cad55cb5e77f1cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770224"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="3c284-102">Metodo ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="3c284-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="3c284-103">Consente di nuovo o in sospeso alle richieste di interruzione di thread ottengano in thread viene interrotto nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3c284-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c284-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c284-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3c284-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c284-105">Return Value</span></span>  
 <span data-ttu-id="3c284-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="3c284-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3c284-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c284-107">HRESULT</span></span>|<span data-ttu-id="3c284-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c284-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c284-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c284-109">S_OK</span></span>|<span data-ttu-id="3c284-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c284-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="3c284-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="3c284-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="3c284-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3c284-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c284-113">Note</span><span class="sxs-lookup"><span data-stu-id="3c284-113">Remarks</span></span>  
 <span data-ttu-id="3c284-114">La chiamata a questa interruzione del thread ritardo decrementa il contatore di metodo per il thread corrente di uno.</span><span class="sxs-lookup"><span data-stu-id="3c284-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="3c284-115">Le chiamate a [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) e `EndPreventAsyncAbort` possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="3c284-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="3c284-116">Ritardo fino a quando il contatore è maggiore di zero, interruzioni di thread per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3c284-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="3c284-117">La funzionalità che viene esposto da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="3c284-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="3c284-118">Un uso improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="3c284-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="3c284-119">Ad esempio, chiamando `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` è stato possibile impostare il contatore a zero quando la macchina virtuale in precedenza ha incrementato in.</span><span class="sxs-lookup"><span data-stu-id="3c284-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="3c284-120">Analogamente, il contatore interno non viene controllato dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="3c284-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="3c284-121">Se l'utilizzo supera il limite di integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.</span><span class="sxs-lookup"><span data-stu-id="3c284-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c284-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c284-122">Requirements</span></span>  
 <span data-ttu-id="3c284-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c284-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c284-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c284-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c284-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3c284-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c284-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c284-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c284-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c284-127">See also</span></span>

- [<span data-ttu-id="3c284-128">Metodo BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="3c284-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="3c284-129">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="3c284-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="3c284-130">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3c284-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3c284-131">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="3c284-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3c284-132">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3c284-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3c284-133">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3c284-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
