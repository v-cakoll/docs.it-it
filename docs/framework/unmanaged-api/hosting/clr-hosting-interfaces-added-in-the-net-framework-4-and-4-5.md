---
title: Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982f5780a40dd8cbce02ec33f7e6f77589cd3717
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435796"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="ef1a3-102">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="ef1a3-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="ef1a3-103">Questa sezione vengono descritte le interfacce non gestite host consente di integrare common language runtime (CLR) nei [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]e versioni successive nelle relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="ef1a3-104">Queste interfacce forniscono metodi per un host configurare e caricare il runtime in un processo.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="ef1a3-105">A partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], hosting tutte le interfacce hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef1a3-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
-   <span data-ttu-id="ef1a3-106">Utilizzano la gestione della durata (`AddRef` e `Release`), incapsulamento (contesto implicito) e `QueryInterface` da COM.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
-   <span data-ttu-id="ef1a3-107">Non utilizzano i tipi COM, ad esempio `BSTR`, `SAFEARRAY`, o `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
-   <span data-ttu-id="ef1a3-108">Non sono presenti modelli di apartment, aggregazione o attivazione del Registro di sistema che utilizzano il [funzione CoCreateInstance](http://go.microsoft.com/fwlink/?LinkId=142894).</span><span class="sxs-lookup"><span data-stu-id="ef1a3-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](http://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef1a3-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ef1a3-109">In This Section</span></span>  
 [<span data-ttu-id="ef1a3-110">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="ef1a3-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="ef1a3-111">Fornisce metodi che controllano un dominio di applicazione e CPU.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="ef1a3-112">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="ef1a3-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="ef1a3-113">Consente all'host specificare la gestione del dominio applicazione che verrà utilizzata per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="ef1a3-114">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="ef1a3-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="ef1a3-115">Fornisce il [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) metodo, che consente a un host impostare le dimensioni del segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori minori `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="ef1a3-116">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ef1a3-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="ef1a3-117">Fornisce metodi che restituiscono una versione specifica di CLR, elencano tutti i runtime installati, l'elenco di tutti i runtime in-process, restituiscono l'interfaccia di attivazione e individuano la versione CLR utilizzata per compilare un assembly.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="ef1a3-118">Interfaccia ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="ef1a3-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="ef1a3-119">Fornisce il [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo che fornisce un'interfaccia CLR in base ai criteri, assembly gestito, versione e file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="ef1a3-120">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ef1a3-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="ef1a3-121">Fornisce metodi che restituiscono informazioni su una specifica del runtime, compresi versione, directory e stato di caricamento.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="ef1a3-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ef1a3-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="ef1a3-123">Fornisce una base funzioni statiche globali per la firma degli assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="ef1a3-124">Tutti i [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) restituiscono valori HRESULT COM standard.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="ef1a3-125">Interfaccia ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="ef1a3-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="ef1a3-126">Fornisce la possibilità di creare nomi sicuri tramite il gruppo di SHA-2 degli algoritmi di Hash di protezione (SHA-256, SHA-384 e SHA-512).</span><span class="sxs-lookup"><span data-stu-id="ef1a3-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="ef1a3-127">Interfaccia ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="ef1a3-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="ef1a3-128">Fornisce tutte le funzionalità del [ICLRTask (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); inoltre, fornisce metodi che consentono l'interruzione di thread per ritardare il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ef1a3-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ef1a3-129">Related Sections</span></span>  
 [<span data-ttu-id="ef1a3-130">Interfacce di hosting CLR deprecate e coclassi</span><span class="sxs-lookup"><span data-stu-id="ef1a3-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="ef1a3-131">Descrive le interfacce di hosting fornite con .NET Framework versioni 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="ef1a3-132">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="ef1a3-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="ef1a3-133">Descrive le interfacce di hosting fornite con le versioni di .NET Framework 2.0, 3.0 e 3.5.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="ef1a3-134">Hosting</span><span class="sxs-lookup"><span data-stu-id="ef1a3-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="ef1a3-135">Viene introdotto l'hosting di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef1a3-135">Introduces hosting in the .NET Framework.</span></span>
