---
title: Interfaccia ICLRAppDomainResourceMonitor
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 597381c8ab31e86a02f870a24f165676d200b66e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965020"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="c2d7e-102">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="c2d7e-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="c2d7e-103">Fornisce metodi che controllano l'utilizzo della CPU e della memoria del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2d7e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c2d7e-104">Methods</span></span>  
  
|<span data-ttu-id="c2d7e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c2d7e-105">Method</span></span>|<span data-ttu-id="c2d7e-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c2d7e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2d7e-107">Metodo GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="c2d7e-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="c2d7e-108">Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio applicazione da quando è stato creato, senza sottrarre memoria che è stata sottoposta a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="c2d7e-109">Metodo GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="c2d7e-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="c2d7e-110">Ottiene il numero di byte esclusi dall'ultimo blocco completo Garbage Collection e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="c2d7e-111">Metodo GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="c2d7e-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="c2d7e-112">Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2d7e-113">Note</span><span class="sxs-lookup"><span data-stu-id="c2d7e-113">Remarks</span></span>  
 <span data-ttu-id="c2d7e-114">L' `ICLRAppDomainResourceMonitor` interfaccia fornisce funzionalità simili alle seguenti proprietà gestite:</span><span class="sxs-lookup"><span data-stu-id="c2d7e-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="c2d7e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2d7e-115">Requirements</span></span>  
 <span data-ttu-id="c2d7e-116">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d7e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d7e-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c2d7e-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c2d7e-118">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c2d7e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2d7e-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d7e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d7e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2d7e-120">See also</span></span>

- [<span data-ttu-id="c2d7e-121">\<Elemento > appDomainResourceMonitoring</span><span class="sxs-lookup"><span data-stu-id="c2d7e-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="c2d7e-122">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="c2d7e-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="c2d7e-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c2d7e-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c2d7e-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="c2d7e-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
