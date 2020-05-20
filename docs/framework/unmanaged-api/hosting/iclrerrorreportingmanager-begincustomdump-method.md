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
ms.openlocfilehash: 4c83ffaf920abe005ba987e0a744e13aa0d3c016
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615670"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="18e6b-102">Metodo ICLRErrorReportingManager::BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="18e6b-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="18e6b-103">Specifica la configurazione dei dump dell'heap personalizzati per la segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="18e6b-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18e6b-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18e6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18e6b-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="18e6b-106">in Valore [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) che indica il tipo di dump dell'heap su cui compilare il dump dell'heap personalizzato.</span><span class="sxs-lookup"><span data-stu-id="18e6b-106">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="18e6b-107">in Lunghezza della `items` matrice.</span><span class="sxs-lookup"><span data-stu-id="18e6b-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="18e6b-108">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `dwNumItems` deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="18e6b-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="18e6b-109">in Matrice di istanze di [CustomDumpItem](customdumpitem-structure.md) , che specifica gli elementi da aggiungere al minidump.</span><span class="sxs-lookup"><span data-stu-id="18e6b-109">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="18e6b-110">Se `dwFlavor` non è DUMP_FLAVOR_Mini, `items` deve essere null.</span><span class="sxs-lookup"><span data-stu-id="18e6b-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="18e6b-111">[in] Riservato per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="18e6b-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18e6b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="18e6b-112">Return Value</span></span>  
  
|<span data-ttu-id="18e6b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18e6b-113">HRESULT</span></span>|<span data-ttu-id="18e6b-114">Description</span><span class="sxs-lookup"><span data-stu-id="18e6b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18e6b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="18e6b-115">S_OK</span></span>|<span data-ttu-id="18e6b-116">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="18e6b-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="18e6b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="18e6b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18e6b-118">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="18e6b-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18e6b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18e6b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18e6b-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="18e6b-120">The call timed out.</span></span>|  
|<span data-ttu-id="18e6b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18e6b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18e6b-122">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="18e6b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18e6b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18e6b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18e6b-124">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="18e6b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18e6b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18e6b-125">E_FAIL</span></span>|<span data-ttu-id="18e6b-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="18e6b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="18e6b-127">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="18e6b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18e6b-128">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="18e6b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18e6b-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="18e6b-129">Remarks</span></span>  
 <span data-ttu-id="18e6b-130">Il `BeginCustomDump` metodo imposta la configurazione del dump dell'heap personalizzato.</span><span class="sxs-lookup"><span data-stu-id="18e6b-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="18e6b-131">Il metodo [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) Cancella la configurazione del dump dell'heap personalizzato e libera qualsiasi stato associato.</span><span class="sxs-lookup"><span data-stu-id="18e6b-131">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="18e6b-132">Deve essere chiamato dopo il completamento del dump dell'heap personalizzato.</span><span class="sxs-lookup"><span data-stu-id="18e6b-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="18e6b-133">La mancata chiamata `EndCustomDump` causa la perdita della memoria.</span><span class="sxs-lookup"><span data-stu-id="18e6b-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e6b-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18e6b-134">Requirements</span></span>  
 <span data-ttu-id="18e6b-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18e6b-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e6b-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="18e6b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18e6b-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18e6b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18e6b-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e6b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e6b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18e6b-139">See also</span></span>

- [<span data-ttu-id="18e6b-140">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="18e6b-140">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="18e6b-141">Enumerazione ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="18e6b-141">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="18e6b-142">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="18e6b-142">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
