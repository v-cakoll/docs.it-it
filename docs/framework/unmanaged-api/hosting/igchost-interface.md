---
title: Interfaccia IGCHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77a2cab35785aa39571d39bdd369fa26cdbcd1d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="igchost-interface"></a><span data-ttu-id="8e274-102">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="8e274-102">IGCHost Interface</span></span>
<span data-ttu-id="8e274-103">Fornisce metodi per ottenere informazioni sul sistema di garbage collection e per controllare alcuni aspetti dell'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8e274-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e274-104">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile utilizzare il [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e la dimensione massima della generazione del sistema di garbage collection 0 su valori minori di `DWORD` limite imposto dal [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8e274-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e274-105">Questa interfaccia è solo utilizzo esperto di dominio.</span><span class="sxs-lookup"><span data-stu-id="8e274-105">This interface is for expert usage only.</span></span> <span data-ttu-id="8e274-106">Le prestazioni di un'applicazione può influire se utilizzato in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="8e274-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e274-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="8e274-107">Methods</span></span>  
  
|<span data-ttu-id="8e274-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="8e274-108">Method</span></span>|<span data-ttu-id="8e274-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e274-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e274-110">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="8e274-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="8e274-111">Forza una raccolta per la generazione specificata, indipendentemente dallo stato dell'operazione di garbage collection corrente.</span><span class="sxs-lookup"><span data-stu-id="8e274-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="8e274-112">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="8e274-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="8e274-113">Ottiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8e274-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="8e274-114">Metodo GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="8e274-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="8e274-115">Ottiene le statistiche per ogni thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8e274-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="8e274-116">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="8e274-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="8e274-117">Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="8e274-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="8e274-118">Metodo SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="8e274-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="8e274-119">Imposta la dimensione massima di memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="8e274-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e274-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e274-120">Requirements</span></span>  
 <span data-ttu-id="8e274-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e274-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e274-122">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="8e274-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8e274-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e274-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e274-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e274-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e274-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e274-125">See Also</span></span>  
 [<span data-ttu-id="8e274-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8e274-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8e274-127">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8e274-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
