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
ms.openlocfilehash: 9d6c9d22f4e50c21e2f41b7efd402907ff5843db
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805221"
---
# <a name="igchost-interface"></a><span data-ttu-id="ef10f-102">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="ef10f-102">IGCHost Interface</span></span>
<span data-ttu-id="ef10f-103">Fornisce metodi per ottenere informazioni sul sistema Garbage Collection e per controllare alcuni aspetti di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ef10f-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef10f-104">A partire da .NET Framework 4,5, è possibile usare il metodo [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) per impostare le dimensioni di un segmento di Garbage Collection e le dimensioni massime della generazione 0 del sistema di Garbage Collection su valori maggiori del `DWORD` limite imposto dal metodo [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ef10f-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef10f-105">Questa interfaccia è solo per uso esperto.</span><span class="sxs-lookup"><span data-stu-id="ef10f-105">This interface is for expert usage only.</span></span> <span data-ttu-id="ef10f-106">Può influire sulle prestazioni di un'applicazione se utilizzata in modo errato.</span><span class="sxs-lookup"><span data-stu-id="ef10f-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef10f-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="ef10f-107">Methods</span></span>  
  
|<span data-ttu-id="ef10f-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="ef10f-108">Method</span></span>|<span data-ttu-id="ef10f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef10f-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef10f-110">Metodo Collect</span><span class="sxs-lookup"><span data-stu-id="ef10f-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="ef10f-111">Impone l'esecuzione di una raccolta per la generazione specificata, indipendentemente dallo stato della Garbage Collection corrente.</span><span class="sxs-lookup"><span data-stu-id="ef10f-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="ef10f-112">Metodo GetStats</span><span class="sxs-lookup"><span data-stu-id="ef10f-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="ef10f-113">Ottiene le statistiche per lo stato corrente del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ef10f-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="ef10f-114">Metodo GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="ef10f-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="ef10f-115">Ottiene le statistiche per thread per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ef10f-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="ef10f-116">Metodo SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="ef10f-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="ef10f-117">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="ef10f-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="ef10f-118">Metodo SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="ef10f-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="ef10f-119">Imposta la dimensione massima della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="ef10f-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef10f-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef10f-120">Requirements</span></span>  
 <span data-ttu-id="ef10f-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef10f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef10f-122">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="ef10f-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ef10f-123">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef10f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef10f-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef10f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef10f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef10f-125">See also</span></span>

- [<span data-ttu-id="ef10f-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ef10f-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ef10f-127">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ef10f-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
