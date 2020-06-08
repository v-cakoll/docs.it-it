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
ms.openlocfilehash: 72caac0aafe7f9c5919057a6ad2565258aec6a50
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504079"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="3492f-102">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3492f-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="3492f-103">Fornisce una funzionalità simile a quella dell'interfaccia [ICorRuntimeHost](icorruntimehost-interface.md) fornita in .NET Framework versione 1, con le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="3492f-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="3492f-104">Aggiunta del metodo [SetHostControl](iclrruntimehost-sethostcontrol-method.md) per impostare l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="3492f-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="3492f-105">Omissione di alcuni metodi forniti da `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="3492f-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3492f-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="3492f-106">Methods</span></span>  
  
|<span data-ttu-id="3492f-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="3492f-107">Method</span></span>|<span data-ttu-id="3492f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3492f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3492f-109">Metodo ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="3492f-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="3492f-110">Utilizzato negli scenari di distribuzione ClickOnce basati su manifesto per specificare l'applicazione da attivare in un nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="3492f-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="3492f-111">Metodo ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="3492f-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="3492f-112">Specifica l'oggetto <xref:System.AppDomain> in cui eseguire il codice gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="3492f-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="3492f-113">Metodo ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="3492f-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="3492f-114">Richiama il metodo specificato del tipo specificato nell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="3492f-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="3492f-115">Metodo GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="3492f-115">GetCLRControl Method</span></span>](iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="3492f-116">Ottiene un puntatore a interfaccia di tipo [ICLRControl](iclrcontrol-interface.md) che può essere utilizzato dagli host per personalizzare gli aspetti del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3492f-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="3492f-117">Metodo GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="3492f-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="3492f-118">Ottiene l'identificatore numerico dell'oggetto <xref:System.AppDomain> attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3492f-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="3492f-119">Metodo SetHostControl</span><span class="sxs-lookup"><span data-stu-id="3492f-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="3492f-120">Imposta l'interfaccia del controllo host.</span><span class="sxs-lookup"><span data-stu-id="3492f-120">Sets the host control interface.</span></span> <span data-ttu-id="3492f-121">È necessario chiamare `SetHostControl` prima di chiamare `Start` .</span><span class="sxs-lookup"><span data-stu-id="3492f-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="3492f-122">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="3492f-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="3492f-123">Inizializza il CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="3492f-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="3492f-124">Metodo Stop</span><span class="sxs-lookup"><span data-stu-id="3492f-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="3492f-125">Arresta l'esecuzione del codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="3492f-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="3492f-126">Metodo UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3492f-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="3492f-127">Scarica l'oggetto <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="3492f-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3492f-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3492f-128">Remarks</span></span>  
 <span data-ttu-id="3492f-129">A partire da .NET Framework 4, usare l'interfaccia [ICLRMetaHost](iclrmetahost-interface.md) per ottenere un puntatore all'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) e quindi chiamare il metodo [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) per ottenere un puntatore a `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="3492f-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="3492f-130">Nelle versioni precedenti del .NET Framework, l'host ottiene un puntatore a un' `ICLRRuntimeHost` istanza chiamando [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="3492f-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="3492f-131">Per fornire implementazioni di qualsiasi tecnologia fornita nella .NET Framework versione 2,0, è necessario usare `ICLRRuntimeHost` anziché `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="3492f-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3492f-132">Non chiamare il metodo [Start](iclrruntimehost-start-method.md) prima di chiamare il metodo [ExecuteApplication](iclrruntimehost-executeapplication-method.md) per attivare un'applicazione basata su manifesto.</span><span class="sxs-lookup"><span data-stu-id="3492f-132">Do not call the [Start](iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="3492f-133">Se il `Start` metodo viene chiamato per primo, la `ExecuteApplication` chiamata al metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3492f-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3492f-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3492f-134">Requirements</span></span>  
 <span data-ttu-id="3492f-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3492f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3492f-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3492f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3492f-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3492f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3492f-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3492f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3492f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3492f-139">See also</span></span>

- [<span data-ttu-id="3492f-140">Funzione CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="3492f-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="3492f-141">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="3492f-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="3492f-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3492f-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3492f-143">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3492f-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="3492f-144">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3492f-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3492f-145">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3492f-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
