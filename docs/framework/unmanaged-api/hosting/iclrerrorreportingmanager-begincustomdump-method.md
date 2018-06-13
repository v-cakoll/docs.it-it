---
title: Metodo ICLRErrorReportingManager::BeginCustomDump
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5d58a90901b7d7cb80ea7f25401b857b4d4875e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434512"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="8b4d2-102">Metodo ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="8b4d2-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="8b4d2-103">Specifica la configurazione di dump dell'heap personalizzati per la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b4d2-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b4d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b4d2-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="8b4d2-106">[in] Oggetto [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) valore che indica il tipo di dump dell'heap in base al quale compilare il dump dell'heap personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="8b4d2-107">[in] La lunghezza del `items` matrice.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="8b4d2-108">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `dwNumItems` deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="8b4d2-109">[in] Matrice di [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze, che specifica gli elementi da aggiungere al minidump.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="8b4d2-110">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `items` deve essere null.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="8b4d2-111">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b4d2-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8b4d2-112">Return Value</span></span>  
  
|<span data-ttu-id="8b4d2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b4d2-113">HRESULT</span></span>|<span data-ttu-id="8b4d2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b4d2-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b4d2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b4d2-115">S_OK</span></span>|<span data-ttu-id="8b4d2-116">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="8b4d2-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b4d2-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b4d2-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b4d2-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b4d2-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b4d2-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-120">The call timed out.</span></span>|  
|<span data-ttu-id="8b4d2-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b4d2-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b4d2-122">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b4d2-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b4d2-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b4d2-124">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b4d2-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b4d2-125">E_FAIL</span></span>|<span data-ttu-id="8b4d2-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b4d2-127">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b4d2-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b4d2-129">Note</span><span class="sxs-lookup"><span data-stu-id="8b4d2-129">Remarks</span></span>  
 <span data-ttu-id="8b4d2-130">Il `BeginCustomDump` metodo imposta la configurazione di dump dell'heap personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="8b4d2-131">Il [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) metodo cancella la configurazione di dump dell'heap personalizzati e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="8b4d2-132">Deve essere chiamato dopo il dump dell'heap personalizzata è stato completato.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b4d2-133">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="8b4d2-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b4d2-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b4d2-134">Requirements</span></span>  
 <span data-ttu-id="8b4d2-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b4d2-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b4d2-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8b4d2-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b4d2-137">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8b4d2-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b4d2-138">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b4d2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4d2-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b4d2-139">See Also</span></span>  
 [<span data-ttu-id="8b4d2-140">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="8b4d2-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="8b4d2-141">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="8b4d2-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="8b4d2-142">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="8b4d2-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
