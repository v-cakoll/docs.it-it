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
ms.openlocfilehash: dd1aa4089a981d82ae1403189343694a065a701d
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703656"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="0c34c-102">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c34c-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="0c34c-103">Fornisce una funzionalità simile a quella dell'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) fornita in .NET Framework versione 1, con le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c34c-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="0c34c-104">Aggiunta del metodo [SetHostControl](iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="0c34c-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="0c34c-105">Omissione di alcuni metodi forniti da `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="0c34c-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c34c-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="0c34c-106">Methods</span></span>  
  
|<span data-ttu-id="0c34c-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="0c34c-107">Method</span></span>|<span data-ttu-id="0c34c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c34c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c34c-109">Metodo ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="0c34c-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="0c34c-110">Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="0c34c-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="0c34c-111">Metodo ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="0c34c-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="0c34c-112">Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="0c34c-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="0c34c-113">Metodo ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="0c34c-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="0c34c-114">Richiama il metodo specificato del tipo specificato nell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="0c34c-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="0c34c-115">Metodo GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="0c34c-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="0c34c-116">Ottiene un puntatore a interfaccia di tipo [ICLRControl](iclrcontrol-interface.md) che può essere utilizzato dagli host per personalizzare gli aspetti del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0c34c-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="0c34c-117">Metodo GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="0c34c-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="0c34c-118">Ottiene l'identificatore numerico dell'oggetto <xref:System.AppDomain> attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c34c-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="0c34c-119">Metodo SetHostControl</span><span class="sxs-lookup"><span data-stu-id="0c34c-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="0c34c-120">Imposta l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="0c34c-120">Sets the host control interface.</span></span> <span data-ttu-id="0c34c-121">È necessario chiamare `SetHostControl` prima di chiamare `Start` .</span><span class="sxs-lookup"><span data-stu-id="0c34c-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="0c34c-122">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="0c34c-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="0c34c-123">Inizializza il CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="0c34c-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="0c34c-124">Metodo Stop</span><span class="sxs-lookup"><span data-stu-id="0c34c-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="0c34c-125">Arresta l'esecuzione del codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="0c34c-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="0c34c-126">Metodo UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0c34c-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="0c34c-127">Scarica l'oggetto <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="0c34c-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c34c-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c34c-128">Remarks</span></span>  
 <span data-ttu-id="0c34c-129">A partire da .NET Framework 4, usare l'interfaccia [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) per ottenere un puntatore all'interfaccia [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) e quindi chiamare il metodo [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) per ottenere un puntatore a `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="0c34c-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="0c34c-130">Nelle versioni precedenti del .NET Framework, l'host ottiene un puntatore a un' `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="0c34c-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="0c34c-131">Per fornire implementazioni di qualsiasi tecnologia fornita nella .NET Framework versione 2,0, è necessario usare `ICLRRuntimeHost` anziché `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="0c34c-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0c34c-132">Non chiamare il metodo [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) prima di chiamare il metodo [ExecuteApplication](iclrruntimehost-executeapplication-method.md) per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="0c34c-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="0c34c-133">Se il `Start` metodo viene chiamato per primo, la `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0c34c-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c34c-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c34c-134">Requirements</span></span>  
 <span data-ttu-id="0c34c-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c34c-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c34c-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0c34c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c34c-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c34c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c34c-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c34c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c34c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c34c-139">See also</span></span>

- [<span data-ttu-id="0c34c-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="0c34c-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="0c34c-141">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="0c34c-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="0c34c-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0c34c-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0c34c-143">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c34c-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="0c34c-144">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0c34c-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0c34c-145">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c34c-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
