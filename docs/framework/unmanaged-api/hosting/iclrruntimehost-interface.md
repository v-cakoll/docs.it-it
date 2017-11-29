---
title: Interfaccia ICLRRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost
helpviewer_keywords: ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type: apiref
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 332db2680ca23f34893a6c50c5311d73838bc1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="6f63c-102">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6f63c-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="6f63c-103">Fornisce una funzionalità simile a quello del [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaccia fornita in .NET Framework versione 1, con le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f63c-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="6f63c-104">L'aggiunta del [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="6f63c-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="6f63c-105">L'omissione di alcuni metodi forniti da `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="6f63c-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f63c-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="6f63c-106">Methods</span></span>  
  
|<span data-ttu-id="6f63c-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="6f63c-107">Method</span></span>|<span data-ttu-id="6f63c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f63c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f63c-109">ExecuteApplication (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="6f63c-110">Utilizzato in scenari di distribuzione basato su manifesto ClickOnce per specificare l'attivazione in un nuovo dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f63c-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="6f63c-111">ExecuteInAppDomain (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="6f63c-112">Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="6f63c-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="6f63c-113">ExecuteInDefaultAppDomain (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="6f63c-114">Richiama il metodo specificato nel tipo specificato nell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="6f63c-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="6f63c-115">GetCLRControl (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="6f63c-116">Ottiene un puntatore a interfaccia di tipo [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che gli host possono usare per personalizzare gli aspetti di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6f63c-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="6f63c-117">GetCurrentAppDomainId (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="6f63c-118">Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6f63c-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="6f63c-119">SetHostControl (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="6f63c-120">Imposta l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="6f63c-120">Sets the host control interface.</span></span> <span data-ttu-id="6f63c-121">È necessario chiamare `SetHostControl` prima di chiamare `Start`.</span><span class="sxs-lookup"><span data-stu-id="6f63c-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="6f63c-122">Start (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="6f63c-123">Inizializza il CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="6f63c-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="6f63c-124">Stop (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="6f63c-125">Arresta l'esecuzione di codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="6f63c-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="6f63c-126">UnloadAppDomain (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f63c-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="6f63c-127">Consente di scaricare il <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="6f63c-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f63c-128">Note</span><span class="sxs-lookup"><span data-stu-id="6f63c-128">Remarks</span></span>  
 <span data-ttu-id="6f63c-129">A partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], utilizzare il [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interfaccia da ottenere un puntatore al [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia e quindi chiamare il [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) metodo per ottenere un puntatore a `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="6f63c-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="6f63c-130">Nelle versioni precedenti di .NET Framework, l'host ottiene un puntatore a un `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="6f63c-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="6f63c-131">Per fornire l'implementazione delle tecnologie fornite con .NET Framework versione 2.0, è necessario utilizzare `ICLRRuntimeHost` anziché `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="6f63c-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f63c-132">Non chiamare il [avviare](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo prima di chiamare il [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) metodo per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="6f63c-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="6f63c-133">Se il `Start` metodo viene chiamato per primo, il `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6f63c-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f63c-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f63c-134">Requirements</span></span>  
 <span data-ttu-id="6f63c-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f63c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f63c-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6f63c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f63c-137">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f63c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f63c-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f63c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f63c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f63c-139">See Also</span></span>  
 [<span data-ttu-id="6f63c-140">CorBindToCurrentRuntime (funzione)</span><span class="sxs-lookup"><span data-stu-id="6f63c-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="6f63c-141">CorBindToRuntimeEx (funzione)</span><span class="sxs-lookup"><span data-stu-id="6f63c-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="6f63c-142">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6f63c-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="6f63c-143">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6f63c-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="6f63c-144">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6f63c-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6f63c-145">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6f63c-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
