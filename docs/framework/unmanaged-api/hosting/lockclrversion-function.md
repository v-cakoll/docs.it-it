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
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133768"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="f0f0c-102">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="f0f0c-102">LockClrVersion Function</span></span>
<span data-ttu-id="f0f0c-103">Consente all'host di determinare quale versione di Common Language Runtime (CLR) verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="f0f0c-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f0c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0f0c-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f0c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0f0c-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="f0f0c-107">in Funzione che deve essere chiamata da CLR dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="f0f0c-108">in Funzione che deve essere chiamata dall'host per informare il CLR che l'inizializzazione è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="f0f0c-109">in Funzione che deve essere chiamata dall'host per informare CLR che l'inizializzazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0f0c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f0f0c-110">Return Value</span></span>  
 <span data-ttu-id="f0f0c-111">Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f0f0c-112">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="f0f0c-112">Return code</span></span>|<span data-ttu-id="f0f0c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0f0c-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f0f0c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0f0c-114">S_OK</span></span>|<span data-ttu-id="f0f0c-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="f0f0c-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f0f0c-116">E_INVALIDARG</span></span>|<span data-ttu-id="f0f0c-117">Uno o più argomenti sono null.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0f0c-118">Note</span><span class="sxs-lookup"><span data-stu-id="f0f0c-118">Remarks</span></span>  
 <span data-ttu-id="f0f0c-119">L'host chiama `LockClrVersion` prima di inizializzare CLR.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="f0f0c-120">`LockClrVersion` accetta tre parametri, che sono tutti callback di tipo [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="f0f0c-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="f0f0c-121">Questo tipo è definito nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="f0f0c-122">Durante l'inizializzazione del runtime si verificano i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0f0c-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="f0f0c-123">L'host chiama [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="f0f0c-124">In alternativa, l'host potrebbe inizializzare il runtime utilizzando l'attivazione di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="f0f0c-125">Il runtime chiama la funzione specificata dal parametro `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="f0f0c-126">La funzione specificata da `hostCallback` esegue quindi la sequenza di chiamate seguente:</span><span class="sxs-lookup"><span data-stu-id="f0f0c-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="f0f0c-127">Funzione specificata dal parametro `pBeginHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="f0f0c-128">`CorBindToRuntimeEx` o un'altra funzione di inizializzazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="f0f0c-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="f0f0c-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="f0f0c-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="f0f0c-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="f0f0c-131">Funzione specificata dal parametro `pEndHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="f0f0c-132">Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` devono essere eseguite su un singolo thread o Fiber, con lo stesso stack logico.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="f0f0c-133">Questo thread può essere diverso dal thread sul quale viene chiamato `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="f0f0c-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f0c-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0f0c-134">Requirements</span></span>  
 <span data-ttu-id="f0f0c-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0f0c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f0c-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0f0c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0f0c-137">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f0f0c-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0f0c-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f0c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f0c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0f0c-139">See also</span></span>

- [<span data-ttu-id="f0f0c-140">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f0f0c-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
