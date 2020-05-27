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
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008495"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="ee9f8-102">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="ee9f8-102">LockClrVersion Function</span></span>
<span data-ttu-id="ee9f8-103">Consente all'host di determinare quale versione di Common Language Runtime (CLR) verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="ee9f8-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee9f8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee9f8-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee9f8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee9f8-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="ee9f8-107">in Funzione che deve essere chiamata da CLR dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="ee9f8-108">in Funzione che deve essere chiamata dall'host per informare il CLR che l'inizializzazione è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="ee9f8-109">in Funzione che deve essere chiamata dall'host per informare CLR che l'inizializzazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee9f8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee9f8-110">Return Value</span></span>  
 <span data-ttu-id="ee9f8-111">Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ee9f8-112">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="ee9f8-112">Return code</span></span>|<span data-ttu-id="ee9f8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee9f8-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ee9f8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee9f8-114">S_OK</span></span>|<span data-ttu-id="ee9f8-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="ee9f8-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ee9f8-116">E_INVALIDARG</span></span>|<span data-ttu-id="ee9f8-117">Uno o più argomenti sono null.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee9f8-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="ee9f8-118">Remarks</span></span>  
 <span data-ttu-id="ee9f8-119">L'host chiama `LockClrVersion` prima di inizializzare CLR.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="ee9f8-120">`LockClrVersion`accetta tre parametri, che sono tutti callback di tipo [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="ee9f8-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="ee9f8-121">Questo tipo è definito nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="ee9f8-122">Durante l'inizializzazione del runtime si verificano i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee9f8-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="ee9f8-123">L'host chiama [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o una delle altre funzioni di inizializzazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-123">The host calls [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="ee9f8-124">In alternativa, l'host potrebbe inizializzare il runtime utilizzando l'attivazione di oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="ee9f8-125">Il runtime chiama la funzione specificata dal `hostCallback` parametro.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="ee9f8-126">La funzione specificata da `hostCallback` esegue quindi la sequenza di chiamate seguente:</span><span class="sxs-lookup"><span data-stu-id="ee9f8-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="ee9f8-127">Funzione specificata dal `pBeginHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="ee9f8-128">`CorBindToRuntimeEx`(o un'altra funzione di inizializzazione del Runtime).</span><span class="sxs-lookup"><span data-stu-id="ee9f8-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="ee9f8-129">[ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee9f8-129">[ICLRRuntimeHost::SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="ee9f8-130">[ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee9f8-130">[ICLRRuntimeHost::Start](iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="ee9f8-131">Funzione specificata dal `pEndHostSetup` parametro.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="ee9f8-132">Tutte le chiamate da `pBeginHostSetup` a `pEndHostSetup` devono essere eseguite su un singolo thread o Fiber, con lo stesso stack logico.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="ee9f8-133">Questo thread può essere diverso dal thread su cui `hostCallback` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="ee9f8-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee9f8-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee9f8-134">Requirements</span></span>  
 <span data-ttu-id="ee9f8-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee9f8-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee9f8-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee9f8-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee9f8-137">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee9f8-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee9f8-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee9f8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9f8-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee9f8-139">See also</span></span>

- [<span data-ttu-id="ee9f8-140">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ee9f8-140">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
