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
ms.openlocfilehash: 15bdbc001838e3d13a9789c8f54daa80f3b6ef9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985205"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="6855e-102">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="6855e-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="6855e-103">Fornisce metodi per controllare memoria e utilizzo della CPU di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6855e-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6855e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6855e-104">Methods</span></span>  
  
|<span data-ttu-id="6855e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6855e-105">Method</span></span>|<span data-ttu-id="6855e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6855e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6855e-107">Metodo GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="6855e-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="6855e-108">Ottiene la dimensione totale, espressa in byte, di tutte le allocazioni di memoria che sono state apportate dal dominio dell'applicazione perché è stato creato, senza sottrarre la memoria che è stato sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6855e-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="6855e-109">Metodo GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="6855e-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="6855e-110">Ottiene il numero di byte esclusi dall'ultima completa di garbage collection di blocco e che fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="6855e-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="6855e-111">Metodo GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="6855e-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="6855e-112">Ottiene il tempo processore totale che è stato usato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, poiché è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6855e-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6855e-113">Note</span><span class="sxs-lookup"><span data-stu-id="6855e-113">Remarks</span></span>  
 <span data-ttu-id="6855e-114">Il `ICLRAppDomainResourceMonitor` interfaccia fornisce funzionalità simili alle seguenti proprietà gestite:</span><span class="sxs-lookup"><span data-stu-id="6855e-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="6855e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6855e-115">Requirements</span></span>  
 <span data-ttu-id="6855e-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6855e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6855e-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6855e-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6855e-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6855e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6855e-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6855e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6855e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6855e-120">See also</span></span>

- [<span data-ttu-id="6855e-121">\<appDomainResourceMonitoring > elemento</span><span class="sxs-lookup"><span data-stu-id="6855e-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="6855e-122">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6855e-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="6855e-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6855e-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6855e-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="6855e-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
