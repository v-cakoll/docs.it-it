---
title: Funzione LockClrVersion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91bb1a9416e577dbb5cc96e8be87033c53232811
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336694"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="36906-102">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="36906-102">LockClrVersion Function</span></span>
<span data-ttu-id="36906-103">Consente all'host determinare quale versione di common language runtime (CLR) da utilizzare all'interno del processo prima di inizializzare in modo esplicito il CLR.</span><span class="sxs-lookup"><span data-stu-id="36906-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="36906-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36906-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36906-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36906-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36906-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="36906-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="36906-107">[in] La funzione che verrà chiamata da CLR in fase di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="36906-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="36906-108">[in] La funzione da chiamare dall'host per indicare a CLR che l'inizializzazione sta avviando.</span><span class="sxs-lookup"><span data-stu-id="36906-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="36906-109">[in] La funzione da chiamare dall'host per indicare a CLR che l'inizializzazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="36906-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36906-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36906-110">Return Value</span></span>  
 <span data-ttu-id="36906-111">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="36906-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="36906-112">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="36906-112">Return code</span></span>|<span data-ttu-id="36906-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36906-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="36906-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="36906-114">S_OK</span></span>|<span data-ttu-id="36906-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="36906-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="36906-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="36906-116">E_INVALIDARG</span></span>|<span data-ttu-id="36906-117">Uno o più argomenti sono null.</span><span class="sxs-lookup"><span data-stu-id="36906-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36906-118">Note</span><span class="sxs-lookup"><span data-stu-id="36906-118">Remarks</span></span>  
 <span data-ttu-id="36906-119">L'host chiama `LockClrVersion` prima di inizializzare il CLR.</span><span class="sxs-lookup"><span data-stu-id="36906-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> `LockClrVersion` <span data-ttu-id="36906-120">accetta tre parametri, ognuno dei quali sono i callback typu [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="36906-120">takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="36906-121">Questo tipo viene definito come segue.</span><span class="sxs-lookup"><span data-stu-id="36906-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="36906-122">Al momento dell'inizializzazione del runtime vengono eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36906-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="36906-123">L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="36906-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="36906-124">In alternativa, l'host è stato possibile inizializzare il runtime usando l'attivazione di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="36906-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="36906-125">Il runtime chiama la funzione specificata dal `hostCallback` parametro.</span><span class="sxs-lookup"><span data-stu-id="36906-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="36906-126">La funzione specificata da `hostCallback` quindi rende la sequenza di chiamate seguente:</span><span class="sxs-lookup"><span data-stu-id="36906-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="36906-127">La funzione specificata dal `pBeginHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="36906-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   `CorBindToRuntimeEx` <span data-ttu-id="36906-128">(o un'altra funzione di inizializzazione di runtime).</span><span class="sxs-lookup"><span data-stu-id="36906-128">(or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="36906-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="36906-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="36906-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="36906-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="36906-131">La funzione specificata dal `pEndHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="36906-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="36906-132">Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` deve verificarsi su un singolo thread o fiber, con lo stesso stack di logico.</span><span class="sxs-lookup"><span data-stu-id="36906-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="36906-133">Questo thread può essere diverso dal thread su cui `hostCallback` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="36906-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36906-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36906-134">Requirements</span></span>  
 <span data-ttu-id="36906-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36906-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36906-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36906-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36906-137">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36906-137">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="36906-138">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="36906-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36906-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36906-139">See also</span></span>

- [<span data-ttu-id="36906-140">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="36906-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
