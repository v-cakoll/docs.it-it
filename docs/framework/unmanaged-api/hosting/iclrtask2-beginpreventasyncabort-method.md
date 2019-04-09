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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a43fef7f6dfa6dbe0bb9f1c4caec2c9c224b93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213584"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="23bca-102">Metodo ICLRTask2::BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="23bca-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="23bca-103">Ritardi nuove richieste di interruzione dal conseguente interruzioni di thread nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="23bca-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23bca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23bca-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="23bca-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23bca-105">Return Value</span></span>  
 <span data-ttu-id="23bca-106">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="23bca-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="23bca-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23bca-107">HRESULT</span></span>|<span data-ttu-id="23bca-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23bca-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23bca-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="23bca-109">S_OK</span></span>|<span data-ttu-id="23bca-110">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="23bca-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="23bca-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="23bca-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="23bca-112">Il metodo è stato chiamato su un thread che non è il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="23bca-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23bca-113">Note</span><span class="sxs-lookup"><span data-stu-id="23bca-113">Remarks</span></span>  
 <span data-ttu-id="23bca-114">Chiamare questo metodo incrementa il contatore di ritardo di interruzione per il thread corrente di uno.</span><span class="sxs-lookup"><span data-stu-id="23bca-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="23bca-115">Le chiamate a `BeginPreventAsyncAbort` e [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="23bca-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="23bca-116">Ritardo fino a quando il contatore è maggiore di zero, interruzioni di thread per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="23bca-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="23bca-117">Se questa chiamata non è abbinata con una chiamata al `EndPreventAsyncAbort` metodo, è possibile raggiungere uno stato nel quale thread interruzioni non possono essere recapitate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="23bca-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="23bca-118">Il ritardo non viene applicato per un thread che interrompe se stesso.</span><span class="sxs-lookup"><span data-stu-id="23bca-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="23bca-119">La funzionalità che viene esposto da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM).</span><span class="sxs-lookup"><span data-stu-id="23bca-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="23bca-120">Un uso improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="23bca-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="23bca-121">Ad esempio, chiamando `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` è stato possibile impostare il contatore a zero quando la macchina virtuale in precedenza ha incrementato in.</span><span class="sxs-lookup"><span data-stu-id="23bca-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="23bca-122">Analogamente, il contatore interno non viene controllato dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="23bca-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="23bca-123">Se l'utilizzo supera il limite di integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.</span><span class="sxs-lookup"><span data-stu-id="23bca-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23bca-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23bca-124">Requirements</span></span>  
 <span data-ttu-id="23bca-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23bca-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23bca-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23bca-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23bca-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="23bca-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="23bca-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="23bca-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23bca-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23bca-129">See also</span></span>

- [<span data-ttu-id="23bca-130">Metodo EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="23bca-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="23bca-131">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="23bca-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="23bca-132">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="23bca-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="23bca-133">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="23bca-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="23bca-134">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="23bca-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="23bca-135">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="23bca-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
