---
title: Interfaccia ICorRuntimeHost
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
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1280c49c2eea6a06eca10ebd8896b0722e321547
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="629b8-102">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="629b8-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="629b8-103">Fornisce metodi che consentono all'host avviare e arrestare in modo esplicito, common language runtime (CLR) per creare e configurare i domini applicazione, per accedere al dominio predefinito e per enumerare tutti i domini in esecuzione nel processo.</span><span class="sxs-lookup"><span data-stu-id="629b8-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="629b8-104">In .NET Framework versione 2.0, questa interfaccia è stata sostituita da [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="629b8-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="629b8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="629b8-105">Methods</span></span>  
  
|<span data-ttu-id="629b8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="629b8-106">Method</span></span>|<span data-ttu-id="629b8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="629b8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="629b8-108">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="629b8-108">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|<span data-ttu-id="629b8-109">Reimposta un enumeratore di dominio fino all'inizio dell'elenco di domini.</span><span class="sxs-lookup"><span data-stu-id="629b8-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="629b8-110">Metodo CreateDomain</span><span class="sxs-lookup"><span data-stu-id="629b8-110">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|<span data-ttu-id="629b8-111">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="629b8-111">Creates an application domain.</span></span> <span data-ttu-id="629b8-112">Il chiamante riceve un puntatore a interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="629b8-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="629b8-113">Metodo CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="629b8-113">CreateDomainEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|<span data-ttu-id="629b8-114">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="629b8-114">Creates an application domain.</span></span> <span data-ttu-id="629b8-115">Questo metodo consente al chiamante di passare un'istanza di IAppDomainSetup per configurare le funzionalità aggiuntive dell'oggetto restituito <xref:System._AppDomain> istanza.</span><span class="sxs-lookup"><span data-stu-id="629b8-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="629b8-116">Metodo CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="629b8-116">CreateDomainSetup Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="629b8-117">Ottiene un puntatore a interfaccia di tipo `IAppDomainSetup` per un <xref:System.AppDomainSetup> istanza.</span><span class="sxs-lookup"><span data-stu-id="629b8-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="629b8-118">`IAppDomainSetup`fornisce metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.</span><span class="sxs-lookup"><span data-stu-id="629b8-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="629b8-119">Metodo CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="629b8-119">CreateEvidence Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|<span data-ttu-id="629b8-120">Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity>, che consente all'host creare l'evidenza di sicurezza da passare al [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="629b8-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="629b8-121">Metodo CreateLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="629b8-121">CreateLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="629b8-122">Non usare.</span><span class="sxs-lookup"><span data-stu-id="629b8-122">Do not use.</span></span>|  
|[<span data-ttu-id="629b8-123">Metodo CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="629b8-123">CurrentDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|<span data-ttu-id="629b8-124">Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio caricato sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="629b8-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="629b8-125">Metodo DeleteLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="629b8-125">DeleteLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="629b8-126">Non usare.</span><span class="sxs-lookup"><span data-stu-id="629b8-126">Do not use.</span></span>|  
|[<span data-ttu-id="629b8-127">Metodo EnumDomains</span><span class="sxs-lookup"><span data-stu-id="629b8-127">EnumDomains Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|<span data-ttu-id="629b8-128">Ottiene un enumeratore per i domini nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="629b8-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="629b8-129">Metodo GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="629b8-129">GetConfiguration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="629b8-130">Ottiene un oggetto che consente all'host specificare la configurazione di callback di CLR.</span><span class="sxs-lookup"><span data-stu-id="629b8-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="629b8-131">Metodo GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="629b8-131">GetDefaultDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="629b8-132">Ottiene un puntatore a interfaccia di tipo <xref:System._AppDomain> che rappresenta il dominio predefinito per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="629b8-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="629b8-133">Metodo LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="629b8-133">LocksHeldByLogicalThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="629b8-134">Non usare.</span><span class="sxs-lookup"><span data-stu-id="629b8-134">Do not use.</span></span>|  
|[<span data-ttu-id="629b8-135">Metodo MapFile</span><span class="sxs-lookup"><span data-stu-id="629b8-135">MapFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|<span data-ttu-id="629b8-136">Il file specificato viene eseguito il mapping in memoria.</span><span class="sxs-lookup"><span data-stu-id="629b8-136">Maps the specified file into memory.</span></span> <span data-ttu-id="629b8-137">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="629b8-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="629b8-138">Metodo NextDomain</span><span class="sxs-lookup"><span data-stu-id="629b8-138">NextDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|<span data-ttu-id="629b8-139">Ottiene un puntatore a interfaccia per il dominio successivo nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="629b8-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="629b8-140">Metodo Start</span><span class="sxs-lookup"><span data-stu-id="629b8-140">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|<span data-ttu-id="629b8-141">Avvia il CLR.</span><span class="sxs-lookup"><span data-stu-id="629b8-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="629b8-142">Metodo Stop</span><span class="sxs-lookup"><span data-stu-id="629b8-142">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|<span data-ttu-id="629b8-143">Arresta l'esecuzione di codice in fase di esecuzione per il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="629b8-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="629b8-144">Metodo SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="629b8-144">SwitchInLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="629b8-145">Non usare.</span><span class="sxs-lookup"><span data-stu-id="629b8-145">Do not use.</span></span>|  
|[<span data-ttu-id="629b8-146">Metodo SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="629b8-146">SwitchOutLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="629b8-147">Non usare.</span><span class="sxs-lookup"><span data-stu-id="629b8-147">Do not use.</span></span>|  
|[<span data-ttu-id="629b8-148">Metodo UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="629b8-148">UnloadDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="629b8-149">Scarica il dominio di applicazione specificata dal processo corrente.</span><span class="sxs-lookup"><span data-stu-id="629b8-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="629b8-150">Requisiti</span><span class="sxs-lookup"><span data-stu-id="629b8-150">Requirements</span></span>  
 <span data-ttu-id="629b8-151">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="629b8-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="629b8-152">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="629b8-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="629b8-153">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="629b8-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="629b8-154">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="629b8-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629b8-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="629b8-155">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="629b8-156">Hosting</span><span class="sxs-lookup"><span data-stu-id="629b8-156">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="629b8-157">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="629b8-157">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="629b8-158">Host di runtime</span><span class="sxs-lookup"><span data-stu-id="629b8-158">Runtime Hosts</span></span>](http://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [<span data-ttu-id="629b8-159">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="629b8-159">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="629b8-160">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="629b8-160">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
