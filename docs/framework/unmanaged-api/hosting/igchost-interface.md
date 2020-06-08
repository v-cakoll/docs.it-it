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
ms.openlocfilehash: 6b6f2dbaa49c29f6614e9c39a3f408d4d1453983
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501625"
---
# <a name="igchost-interface"></a><span data-ttu-id="fc111-102">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="fc111-102">IGCHost Interface</span></span>
<span data-ttu-id="fc111-103">Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fc111-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc111-104">A partire da .NET Framework 4,5, è possibile usare il metodo [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection su valori maggiori del `DWORD` limite imposto dal metodo [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc111-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc111-105">Questa interfaccia è solo per uso esperto.</span><span class="sxs-lookup"><span data-stu-id="fc111-105">This interface is for expert usage only.</span></span> <span data-ttu-id="fc111-106">Può influire sulle prestazioni di un'applicazione se utilizzata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="fc111-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc111-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="fc111-107">Methods</span></span>  
  
|<span data-ttu-id="fc111-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="fc111-108">Method</span></span>|<span data-ttu-id="fc111-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc111-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc111-110">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="fc111-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="fc111-111">Impone l'esecuzione di una raccolta per la generazione specificata, indipendentemente dallo stato della Garbage Collection corrente.</span><span class="sxs-lookup"><span data-stu-id="fc111-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="fc111-112">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="fc111-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="fc111-113">Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fc111-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="fc111-114">Metodo GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="fc111-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="fc111-115">Ottiene le statistiche per thread per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fc111-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="fc111-116">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="fc111-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="fc111-117">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="fc111-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="fc111-118">Metodo SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="fc111-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="fc111-119">Imposta la dimensione massima della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="fc111-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc111-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc111-120">Requirements</span></span>  
 <span data-ttu-id="fc111-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc111-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc111-122">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="fc111-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fc111-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc111-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc111-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc111-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc111-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc111-125">See also</span></span>

- [<span data-ttu-id="fc111-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="fc111-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fc111-127">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="fc111-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
