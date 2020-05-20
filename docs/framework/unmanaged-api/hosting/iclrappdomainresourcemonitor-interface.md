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
ms.openlocfilehash: 08dc0f0891d960cb7b402b30455e606aaff7bcea
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616008"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="4c788-102">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="4c788-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="4c788-103">Fornisce metodi che controllano l'utilizzo della CPU e della memoria del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4c788-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c788-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4c788-104">Methods</span></span>  
  
|<span data-ttu-id="4c788-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4c788-105">Method</span></span>|<span data-ttu-id="4c788-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c788-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c788-107">Metodo GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="4c788-107">GetCurrentAllocated Method</span></span>](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="4c788-108">Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio applicazione da quando è stato creato, senza sottrarre memoria che è stata sottoposta a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4c788-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="4c788-109">Metodo GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="4c788-109">GetCurrentSurvived Method</span></span>](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="4c788-110">Ottiene il numero di byte esclusi dall'ultimo blocco completo Garbage Collection e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="4c788-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="4c788-111">Metodo GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="4c788-111">GetCurrentCpuTime Method</span></span>](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="4c788-112">Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4c788-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c788-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4c788-113">Remarks</span></span>  
 <span data-ttu-id="4c788-114">L' `ICLRAppDomainResourceMonitor` interfaccia fornisce funzionalità simili alle seguenti proprietà gestite:</span><span class="sxs-lookup"><span data-stu-id="4c788-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="4c788-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c788-115">Requirements</span></span>  
 <span data-ttu-id="4c788-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c788-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c788-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4c788-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4c788-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4c788-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c788-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c788-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c788-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c788-120">See also</span></span>

- [<span data-ttu-id="4c788-121">\<Elemento> appDomainResourceMonitoring</span><span class="sxs-lookup"><span data-stu-id="4c788-121">\<appDomainResourceMonitoring> Element</span></span>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="4c788-122">Monitoraggio delle risorse del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="4c788-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="4c788-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4c788-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4c788-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="4c788-124">Hosting</span></span>](index.md)
