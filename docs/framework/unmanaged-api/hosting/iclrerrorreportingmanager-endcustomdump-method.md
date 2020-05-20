---
title: Metodo ICLRErrorReportingManager::EndCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
ms.openlocfilehash: 704d8d0921e671e4172fa6e0ae3f14c4908f289a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615657"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="60983-102">Metodo ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="60983-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="60983-103">Rimuove la configurazione del dump dello stack personalizzato specificata in una chiamata precedente al metodo [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="60983-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60983-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60983-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="60983-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60983-105">Return Value</span></span>  
  
|<span data-ttu-id="60983-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60983-106">HRESULT</span></span>|<span data-ttu-id="60983-107">Description</span><span class="sxs-lookup"><span data-stu-id="60983-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60983-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="60983-108">S_OK</span></span>|<span data-ttu-id="60983-109">`EndCustomDump`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="60983-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="60983-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60983-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60983-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="60983-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60983-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60983-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60983-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="60983-113">The call timed out.</span></span>|  
|<span data-ttu-id="60983-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60983-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60983-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="60983-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60983-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60983-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60983-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="60983-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60983-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60983-118">E_FAIL</span></span>|<span data-ttu-id="60983-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="60983-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60983-120">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="60983-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60983-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60983-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60983-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="60983-122">Remarks</span></span>  
 <span data-ttu-id="60983-123">Il `EndCustomDump` metodo cancella la configurazione del dump dello stack personalizzato impostata da una chiamata precedente al `BeginCustomDump` metodo e libera qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="60983-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="60983-124">Deve essere chiamato dopo il completamento del dump dello stack personalizzato.</span><span class="sxs-lookup"><span data-stu-id="60983-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="60983-125">La mancata chiamata `EndCustomDump` causa la perdita della memoria.</span><span class="sxs-lookup"><span data-stu-id="60983-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60983-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60983-126">Requirements</span></span>  
 <span data-ttu-id="60983-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60983-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60983-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60983-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60983-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="60983-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60983-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60983-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60983-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60983-131">See also</span></span>

- [<span data-ttu-id="60983-132">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="60983-132">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="60983-133">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="60983-133">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="60983-134">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="60983-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
