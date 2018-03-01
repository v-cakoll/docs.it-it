---
title: Metodo ICLRErrorReportingManager::BeginCustomDump
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d09afd9fe0a2905c79ffb2d50b342041865b593b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="7de62-102">Metodo ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="7de62-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="7de62-103">Specifica la configurazione di dump dell'heap personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="7de62-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7de62-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7de62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7de62-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="7de62-106">[in] Oggetto [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) valore che indica il tipo di dump dell'heap in base al quale compilare il dump dell'heap personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7de62-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="7de62-107">[in] La lunghezza del `items` matrice.</span><span class="sxs-lookup"><span data-stu-id="7de62-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="7de62-108">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `dwNumItems` deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="7de62-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="7de62-109">[in] Matrice di [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze, che specifica gli elementi da aggiungere al minidump.</span><span class="sxs-lookup"><span data-stu-id="7de62-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="7de62-110">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `items` deve essere null.</span><span class="sxs-lookup"><span data-stu-id="7de62-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="7de62-111">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="7de62-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7de62-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7de62-112">Return Value</span></span>  
  
|<span data-ttu-id="7de62-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7de62-113">HRESULT</span></span>|<span data-ttu-id="7de62-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7de62-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7de62-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7de62-115">S_OK</span></span>|<span data-ttu-id="7de62-116">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7de62-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="7de62-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7de62-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7de62-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7de62-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7de62-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7de62-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7de62-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7de62-120">The call timed out.</span></span>|  
|<span data-ttu-id="7de62-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7de62-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7de62-122">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7de62-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7de62-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7de62-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7de62-124">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7de62-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7de62-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7de62-125">E_FAIL</span></span>|<span data-ttu-id="7de62-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7de62-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7de62-127">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7de62-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7de62-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7de62-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de62-129">Note</span><span class="sxs-lookup"><span data-stu-id="7de62-129">Remarks</span></span>  
 <span data-ttu-id="7de62-130">Il `BeginCustomDump` metodo imposta la configurazione di dump dell'heap personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7de62-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="7de62-131">Il [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) metodo cancella la configurazione di dump dell'heap personalizzati e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="7de62-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="7de62-132">Deve essere chiamato dopo il dump dell'heap personalizzata è stato completato.</span><span class="sxs-lookup"><span data-stu-id="7de62-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7de62-133">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="7de62-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7de62-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7de62-134">Requirements</span></span>  
 <span data-ttu-id="7de62-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7de62-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7de62-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7de62-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7de62-137">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7de62-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7de62-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7de62-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de62-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7de62-139">See Also</span></span>  
 [<span data-ttu-id="7de62-140">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="7de62-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="7de62-141">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="7de62-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="7de62-142">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="7de62-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
