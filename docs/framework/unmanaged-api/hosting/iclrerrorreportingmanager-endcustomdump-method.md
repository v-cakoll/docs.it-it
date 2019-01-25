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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: addf6f52ad445da372dbb04b9c408c5bfea0daf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660125"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="b2660-102">Metodo ICLRErrorReportingManager::EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="b2660-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="b2660-103">Rimuove la configurazione dump dello stack personalizzati che è stata specificata in una precedente chiamata ai [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b2660-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2660-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2660-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2660-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b2660-105">Return Value</span></span>  
  
|<span data-ttu-id="b2660-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2660-106">HRESULT</span></span>|<span data-ttu-id="b2660-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2660-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2660-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2660-108">S_OK</span></span>|<span data-ttu-id="b2660-109">`EndCustomDump` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2660-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="b2660-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2660-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2660-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2660-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2660-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2660-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2660-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b2660-113">The call timed out.</span></span>|  
|<span data-ttu-id="b2660-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2660-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2660-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b2660-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2660-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2660-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2660-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b2660-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2660-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2660-118">E_FAIL</span></span>|<span data-ttu-id="b2660-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b2660-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2660-120">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b2660-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2660-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2660-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2660-122">Note</span><span class="sxs-lookup"><span data-stu-id="b2660-122">Remarks</span></span>  
 <span data-ttu-id="b2660-123">Il `EndCustomDump` metodo cancella la configurazione dump dello stack personalizzata impostata da una precedente chiamata al `BeginCustomDump` metodo e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="b2660-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="b2660-124">Deve essere chiamato dopo che il dump dello stack personalizzata è stato completato.</span><span class="sxs-lookup"><span data-stu-id="b2660-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2660-125">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="b2660-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2660-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2660-126">Requirements</span></span>  
 <span data-ttu-id="b2660-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2660-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2660-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2660-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2660-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b2660-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2660-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2660-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2660-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2660-131">See also</span></span>
- [<span data-ttu-id="b2660-132">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="b2660-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="b2660-133">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="b2660-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="b2660-134">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="b2660-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
