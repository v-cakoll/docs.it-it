---
title: Interfaccia ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed32fe643a7722eaf1af38e6079096194690e950
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771891"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="9d8a5-102">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9d8a5-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="9d8a5-103">Fornisce funzionalità simili a quelle del [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaccia fornita in .NET Framework versione 1, con le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d8a5-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="9d8a5-104">L'aggiunta del [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) metodo per impostare l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="9d8a5-105">L'omissione di alcuni metodi forniti da `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d8a5-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="9d8a5-106">Methods</span></span>  
  
|<span data-ttu-id="9d8a5-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="9d8a5-107">Method</span></span>|<span data-ttu-id="9d8a5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d8a5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d8a5-109">Metodo ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="9d8a5-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="9d8a5-110">Usato negli scenari di distribuzione ClickOnce basata su manifesto per specificare l'applicazione da attivare in un nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="9d8a5-111">Metodo ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="9d8a5-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="9d8a5-112">Specifica il <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="9d8a5-113">Metodo ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="9d8a5-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="9d8a5-114">Richiama il metodo specificato nel tipo specificato nell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="9d8a5-115">Metodo GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="9d8a5-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="9d8a5-116">Ottiene un puntatore a interfaccia typu [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che gli host possono usare per personalizzare gli aspetti di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9d8a5-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="9d8a5-117">Metodo GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="9d8a5-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="9d8a5-118">Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="9d8a5-119">Metodo SetHostControl</span><span class="sxs-lookup"><span data-stu-id="9d8a5-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="9d8a5-120">Imposta l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-120">Sets the host control interface.</span></span> <span data-ttu-id="9d8a5-121">È necessario chiamare `SetHostControl` prima di chiamare `Start`.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="9d8a5-122">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="9d8a5-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="9d8a5-123">Inizializza CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="9d8a5-124">Metodo Stop</span><span class="sxs-lookup"><span data-stu-id="9d8a5-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="9d8a5-125">Arresta l'esecuzione del codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="9d8a5-126">Metodo UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9d8a5-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="9d8a5-127">Scarica il <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d8a5-128">Note</span><span class="sxs-lookup"><span data-stu-id="9d8a5-128">Remarks</span></span>  
 <span data-ttu-id="9d8a5-129">Inizia con il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], usare il [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) per ottenere un puntatore a interfaccia il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia e quindi chiamare il [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) metodo per ottenere un puntatore a `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="9d8a5-130">Nelle versioni precedenti di .NET Framework, l'host ottiene un puntatore a un `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oppure [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="9d8a5-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="9d8a5-131">Per fornire le implementazioni di tecnologie disponibili in .NET Framework versione 2.0, è necessario utilizzare `ICLRRuntimeHost` invece di `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9d8a5-132">Non chiamare il [avviare](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo prima di chiamare le [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) metodo per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="9d8a5-133">Se il `Start` viene chiamato prima di tutto la `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9d8a5-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d8a5-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d8a5-134">Requirements</span></span>  
 <span data-ttu-id="9d8a5-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d8a5-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d8a5-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9d8a5-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d8a5-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9d8a5-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d8a5-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d8a5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8a5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d8a5-139">See also</span></span>

- [<span data-ttu-id="9d8a5-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="9d8a5-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="9d8a5-141">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="9d8a5-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="9d8a5-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="9d8a5-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9d8a5-143">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9d8a5-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="9d8a5-144">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9d8a5-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9d8a5-145">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9d8a5-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
