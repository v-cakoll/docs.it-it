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
ms.openlocfilehash: 91483d5bdf1eb8e6b03d7691e2a95074e3789317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134873"
---
# <a name="igchost-interface"></a><span data-ttu-id="b6b24-102">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="b6b24-102">IGCHost Interface</span></span>
<span data-ttu-id="b6b24-103">Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6b24-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b24-104">A partire da .NET Framework 4,5, è possibile usare il metodo [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection a valori maggiori del limite `DWORD` viene imposto dal metodo [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b6b24-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b24-105">Questa interfaccia è solo per uso esperto.</span><span class="sxs-lookup"><span data-stu-id="b6b24-105">This interface is for expert usage only.</span></span> <span data-ttu-id="b6b24-106">Può influire sulle prestazioni di un'applicazione se utilizzata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="b6b24-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6b24-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6b24-107">Methods</span></span>  
  
|<span data-ttu-id="b6b24-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="b6b24-108">Method</span></span>|<span data-ttu-id="b6b24-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6b24-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6b24-110">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="b6b24-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="b6b24-111">Impone l'esecuzione di una raccolta per la generazione specificata, indipendentemente dallo stato della Garbage Collection corrente.</span><span class="sxs-lookup"><span data-stu-id="b6b24-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="b6b24-112">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="b6b24-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="b6b24-113">Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6b24-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="b6b24-114">Metodo GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="b6b24-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="b6b24-115">Ottiene le statistiche per thread per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6b24-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="b6b24-116">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="b6b24-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="b6b24-117">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="b6b24-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="b6b24-118">Metodo SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="b6b24-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="b6b24-119">Imposta la dimensione massima della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="b6b24-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6b24-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6b24-120">Requirements</span></span>  
 <span data-ttu-id="b6b24-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b24-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b24-122">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="b6b24-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b6b24-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6b24-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6b24-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b24-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b24-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6b24-125">See also</span></span>

- [<span data-ttu-id="b6b24-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="b6b24-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b6b24-127">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b6b24-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
