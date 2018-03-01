---
title: Interfaccia ICLRAppDomainResourceMonitor
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
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bebd39fce4f6aa6f570b3af348332bf7bcc87ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="fe002-102">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="fe002-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="fe002-103">Fornisce metodi che controllano un dominio di applicazione e CPU.</span><span class="sxs-lookup"><span data-stu-id="fe002-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe002-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fe002-104">Methods</span></span>  
  
|<span data-ttu-id="fe002-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fe002-105">Method</span></span>|<span data-ttu-id="fe002-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe002-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe002-107">Metodo GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="fe002-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="fe002-108">Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio dell'applicazione quando è stato creato, senza sottrarre la memoria che è stato sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="fe002-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="fe002-109">Metodo GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="fe002-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="fe002-110">Ottiene il numero di byte esclusi l'ultima procedura completa di garbage collection bloccante e che fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="fe002-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="fe002-111">Metodo GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="fe002-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="fe002-112">Ottiene il tempo totale del processore utilizzata da tutti i thread durante l'esecuzione nel dominio applicazione corrente, in quanto è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe002-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe002-113">Note</span><span class="sxs-lookup"><span data-stu-id="fe002-113">Remarks</span></span>  
 <span data-ttu-id="fe002-114">Il `ICLRAppDomainResourceMonitor` interfaccia fornisce funzionalità simili alle seguenti proprietà gestite:</span><span class="sxs-lookup"><span data-stu-id="fe002-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
-   <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="fe002-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe002-115">Requirements</span></span>  
 <span data-ttu-id="fe002-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe002-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe002-117">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="fe002-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fe002-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe002-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe002-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe002-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe002-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe002-120">See Also</span></span>  
 [<span data-ttu-id="fe002-121">\<appDomainResourceMonitoring > elemento</span><span class="sxs-lookup"><span data-stu-id="fe002-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [<span data-ttu-id="fe002-122">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="fe002-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="fe002-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="fe002-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="fe002-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="fe002-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
