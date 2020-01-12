---
title: Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: 8484b47549f83795778420048d610e2d1626d87b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899725"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="a42e7-102">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="a42e7-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="a42e7-103">In questa sezione vengono descritte le interfacce che gli host non gestiti possono utilizzare per integrare il Common Language Runtime (CLR) nel .NET Framework 4, .NET Framework 4,5 e versioni successive nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a42e7-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="a42e7-104">Queste interfacce forniscono metodi che consentono a un host di configurare e caricare il runtime in un processo.</span><span class="sxs-lookup"><span data-stu-id="a42e7-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="a42e7-105">A partire da .NET Framework 4, tutte le interfacce di hosting presentano le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="a42e7-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="a42e7-106">Usano la gestione della durata (`AddRef` e `Release`), l'incapsulamento (contesto implicito) e `QueryInterface` da COM.</span><span class="sxs-lookup"><span data-stu-id="a42e7-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="a42e7-107">Non usano tipi COM, ad esempio `BSTR`, `SAFEARRAY`o `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="a42e7-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="a42e7-108">Non sono disponibili modelli di Apartment, aggregazioni o attivazione del registro di sistema che utilizzano la [funzione CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span><span class="sxs-lookup"><span data-stu-id="a42e7-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a42e7-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a42e7-109">In This Section</span></span>  
 [<span data-ttu-id="a42e7-110">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="a42e7-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="a42e7-111">Fornisce metodi che controllano l'utilizzo della CPU e della memoria del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a42e7-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="a42e7-112">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="a42e7-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="a42e7-113">Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="a42e7-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="a42e7-114">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="a42e7-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="a42e7-115">Fornisce il metodo [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) , che consente a un host di impostare le dimensioni del segmento Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection su valori maggiori di `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a42e7-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="a42e7-116">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="a42e7-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="a42e7-117">Fornisce metodi che restituiscono una versione specifica di CLR, elencano tutti i CLR installati, elencano tutti i runtime in-process, restituiscono l'interfaccia di attivazione e individuano la versione CLR utilizzata per compilare un assembly.</span><span class="sxs-lookup"><span data-stu-id="a42e7-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="a42e7-118">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="a42e7-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="a42e7-119">Fornisce il metodo [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) che fornisce un'interfaccia CLR in base ai criteri, all'assembly gestito, alla versione e al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a42e7-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="a42e7-120">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="a42e7-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="a42e7-121">Fornisce metodi che restituiscono informazioni su un runtime specifico, tra cui la versione, la directory e lo stato di caricamento.</span><span class="sxs-lookup"><span data-stu-id="a42e7-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="a42e7-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a42e7-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="a42e7-123">Fornisce funzioni statiche globali di base per la firma di assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="a42e7-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="a42e7-124">Tutti i metodi [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) restituiscono HRESULT COM standard.</span><span class="sxs-lookup"><span data-stu-id="a42e7-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="a42e7-125">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="a42e7-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="a42e7-126">Offre la possibilità di creare nomi sicuri usando il gruppo SHA-2 di algoritmi hash sicuri (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="a42e7-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="a42e7-127">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="a42e7-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="a42e7-128">Fornisce tutte le funzionalità dell' [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a42e7-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a42e7-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a42e7-129">Related Sections</span></span>  
 [<span data-ttu-id="a42e7-130">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="a42e7-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="a42e7-131">Descrive le interfacce di hosting fornite con le versioni .NET Framework 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="a42e7-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="a42e7-132">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="a42e7-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="a42e7-133">Descrive le interfacce di hosting fornite con le versioni .NET Framework 2,0, 3,0 e 3,5.</span><span class="sxs-lookup"><span data-stu-id="a42e7-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="a42e7-134">Hosting</span><span class="sxs-lookup"><span data-stu-id="a42e7-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="a42e7-135">Introduce l'hosting nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a42e7-135">Introduces hosting in the .NET Framework.</span></span>
