---
title: Interfaccia IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228172"
---
# <a name="igchost-interface"></a><span data-ttu-id="43352-102">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="43352-102">IGCHost Interface</span></span>
<span data-ttu-id="43352-103">Fornisce metodi di recupero di informazioni sul sistema di garbage collection e di controllo di alcuni aspetti del processo di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="43352-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43352-104">Inizia con il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile usare il [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo per impostare le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0 sui valori maggiore il `DWORD` limite imposto per la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="43352-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43352-105">Questa interfaccia è per solo all'utilizzo degli esperti.</span><span class="sxs-lookup"><span data-stu-id="43352-105">This interface is for expert usage only.</span></span> <span data-ttu-id="43352-106">Se usato in modo corretto le prestazioni di un'applicazione può influire sulla.</span><span class="sxs-lookup"><span data-stu-id="43352-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43352-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="43352-107">Methods</span></span>  
  
|<span data-ttu-id="43352-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="43352-108">Method</span></span>|<span data-ttu-id="43352-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43352-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43352-110">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="43352-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="43352-111">Forza una raccolta Garbage Collection per la generazione specificata, indipendentemente dallo stato di garbage collection corrente.</span><span class="sxs-lookup"><span data-stu-id="43352-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="43352-112">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="43352-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="43352-113">Ottiene le statistiche per lo stato corrente del sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="43352-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="43352-114">Metodo GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="43352-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="43352-115">Ottiene le statistiche per ogni thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="43352-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="43352-116">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="43352-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="43352-117">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="43352-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="43352-118">Metodo SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="43352-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="43352-119">Imposta la dimensione massima di memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="43352-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43352-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43352-120">Requirements</span></span>  
 <span data-ttu-id="43352-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43352-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43352-122">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="43352-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="43352-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="43352-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="43352-124">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="43352-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43352-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43352-125">See also</span></span>

- [<span data-ttu-id="43352-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="43352-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="43352-127">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="43352-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
