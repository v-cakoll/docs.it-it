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
ms.openlocfilehash: 1d0a85607586a8cdf0a319f2e43d9815d24be21b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772916"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="cbb67-102">Metodo ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="cbb67-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="cbb67-103">Specifica la configurazione dei dump dell'heap personalizzato per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="cbb67-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbb67-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbb67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbb67-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="cbb67-106">[in] Oggetto [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) valore che indica il tipo di dump di heap su cui basare il dump dell'heap personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cbb67-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="cbb67-107">[in] La lunghezza del `items` matrice.</span><span class="sxs-lookup"><span data-stu-id="cbb67-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="cbb67-108">Se `dwFlavor` DUMP_FLAVOR_Mini, non è `dwNumItems` deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="cbb67-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="cbb67-109">[in] Matrice di [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) istanze, che specifica gli elementi da aggiungere al minidump.</span><span class="sxs-lookup"><span data-stu-id="cbb67-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="cbb67-110">Se `dwFlavor` DUMP_FLAVOR_Mini, non è `items` deve essere null.</span><span class="sxs-lookup"><span data-stu-id="cbb67-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="cbb67-111">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="cbb67-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbb67-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cbb67-112">Return Value</span></span>  
  
|<span data-ttu-id="cbb67-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbb67-113">HRESULT</span></span>|<span data-ttu-id="cbb67-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbb67-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cbb67-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbb67-115">S_OK</span></span>|<span data-ttu-id="cbb67-116">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="cbb67-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="cbb67-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cbb67-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cbb67-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cbb67-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cbb67-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbb67-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cbb67-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cbb67-120">The call timed out.</span></span>|  
|<span data-ttu-id="cbb67-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cbb67-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cbb67-122">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="cbb67-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cbb67-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cbb67-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cbb67-124">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cbb67-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cbb67-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cbb67-125">E_FAIL</span></span>|<span data-ttu-id="cbb67-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cbb67-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cbb67-127">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cbb67-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cbb67-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cbb67-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbb67-129">Note</span><span class="sxs-lookup"><span data-stu-id="cbb67-129">Remarks</span></span>  
 <span data-ttu-id="cbb67-130">Il `BeginCustomDump` metodo imposta la configurazione dump dell'heap personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cbb67-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="cbb67-131">Il [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) metodo cancella la configurazione dump dell'heap personalizzato e rilascia qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="cbb67-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="cbb67-132">Deve essere chiamato dopo che il dump dell'heap personalizzato è stato completato.</span><span class="sxs-lookup"><span data-stu-id="cbb67-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cbb67-133">Errore durante la chiamata `EndCustomDump` provoca perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="cbb67-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbb67-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbb67-134">Requirements</span></span>  
 <span data-ttu-id="cbb67-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbb67-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbb67-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbb67-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbb67-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cbb67-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbb67-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb67-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb67-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbb67-139">See also</span></span>

- [<span data-ttu-id="cbb67-140">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="cbb67-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="cbb67-141">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="cbb67-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="cbb67-142">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="cbb67-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
