---
title: Funzione LockClrVersion
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
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a58d7e99f545026f6f133901ef35a1f9b9fabc7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lockclrversion-function"></a><span data-ttu-id="873fb-102">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="873fb-102">LockClrVersion Function</span></span>
<span data-ttu-id="873fb-103">Consente all'host determinare quale versione di common language runtime (CLR) verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito il CLR.</span><span class="sxs-lookup"><span data-stu-id="873fb-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="873fb-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="873fb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873fb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="873fb-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="873fb-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="873fb-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="873fb-107">[in] La funzione deve essere chiamato da Common Language Runtime al momento dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="873fb-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="873fb-108">[in] La funzione di essere chiamato dall'host per indicare a CLR che l'inizializzazione sta avviando.</span><span class="sxs-lookup"><span data-stu-id="873fb-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="873fb-109">[in] La funzione di essere chiamato dall'host per indicare a CLR che l'inizializzazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="873fb-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="873fb-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="873fb-110">Return Value</span></span>  
 <span data-ttu-id="873fb-111">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="873fb-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="873fb-112">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="873fb-112">Return code</span></span>|<span data-ttu-id="873fb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="873fb-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="873fb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="873fb-114">S_OK</span></span>|<span data-ttu-id="873fb-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="873fb-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="873fb-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="873fb-116">E_INVALIDARG</span></span>|<span data-ttu-id="873fb-117">Uno o più argomenti sono null.</span><span class="sxs-lookup"><span data-stu-id="873fb-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="873fb-118">Note</span><span class="sxs-lookup"><span data-stu-id="873fb-118">Remarks</span></span>  
 <span data-ttu-id="873fb-119">L'host chiama `LockClrVersion` prima dell'inizializzazione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="873fb-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="873fb-120">`LockClrVersion`accetta tre parametri, ognuno dei quali sono i callback di tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="873fb-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="873fb-121">Questo tipo viene definito come segue.</span><span class="sxs-lookup"><span data-stu-id="873fb-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="873fb-122">I passaggi seguenti si verificano durante l'inizializzazione del runtime:</span><span class="sxs-lookup"><span data-stu-id="873fb-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="873fb-123">L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="873fb-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="873fb-124">In alternativa, l'host è stato possibile inizializzare il runtime mediante l'attivazione di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="873fb-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="873fb-125">Il runtime chiama la funzione specificata per il `hostCallback` parametro.</span><span class="sxs-lookup"><span data-stu-id="873fb-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="873fb-126">La funzione specificata da `hostCallback` effettua quindi la sequenza di chiamate seguente:</span><span class="sxs-lookup"><span data-stu-id="873fb-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="873fb-127">La funzione specificata per il `pBeginHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="873fb-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   <span data-ttu-id="873fb-128">`CorBindToRuntimeEx`(o un'altra funzione di inizializzazione di runtime).</span><span class="sxs-lookup"><span data-stu-id="873fb-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="873fb-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="873fb-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="873fb-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="873fb-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="873fb-131">La funzione specificata per il `pEndHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="873fb-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="873fb-132">Tutte le chiamate da `pBeginHostSetup` per `pEndHostSetup` deve verificarsi in un solo thread o fiber, con lo stesso stack logico.</span><span class="sxs-lookup"><span data-stu-id="873fb-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="873fb-133">Il thread può essere diverso dal thread su cui `hostCallback` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="873fb-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873fb-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="873fb-134">Requirements</span></span>  
 <span data-ttu-id="873fb-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="873fb-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873fb-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="873fb-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="873fb-137">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="873fb-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="873fb-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873fb-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873fb-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="873fb-139">See Also</span></span>  
 [<span data-ttu-id="873fb-140">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="873fb-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
