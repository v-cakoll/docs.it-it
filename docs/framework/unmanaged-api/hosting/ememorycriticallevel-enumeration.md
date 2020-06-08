---
title: Enumerazione EMemoryCriticalLevel
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 359dd84032fce920892631dda2615f63aa54fa6b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504381"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="58956-102">Enumerazione EMemoryCriticalLevel</span><span class="sxs-lookup"><span data-stu-id="58956-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="58956-103">Contiene valori che indicano l'effetto di un errore quando un'allocazione di memoria specifica è stata richiesta ma non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="58956-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58956-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58956-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="58956-105">Membri</span><span class="sxs-lookup"><span data-stu-id="58956-105">Members</span></span>  
  
|<span data-ttu-id="58956-106">Membro</span><span class="sxs-lookup"><span data-stu-id="58956-106">Member</span></span>|<span data-ttu-id="58956-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58956-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="58956-108">Indica che l'allocazione è essenziale per l'esecuzione di codice gestito nel dominio che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="58956-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="58956-109">Se non è possibile allocare memoria, CLR non può garantire che il dominio sia ancora utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="58956-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="58956-110">L'host decide l'azione da intraprendere quando l'allocazione non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="58956-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="58956-111">Può indicare a CLR di interrompere automaticamente il `AppDomain` o di mantenerne l'esecuzione chiamando metodi su [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="58956-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="58956-112">Indica che l'allocazione è fondamentale per l'esecuzione del codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="58956-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="58956-113">Questo valore viene usato durante l'avvio e durante l'esecuzione di finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="58956-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="58956-114">Se non è possibile allocare memoria, il CLR non può funzionare nel processo.</span><span class="sxs-lookup"><span data-stu-id="58956-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="58956-115">Se l'allocazione ha esito negativo, CLR viene disabilitato in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="58956-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="58956-116">Tutte le chiamate successive a CLR hanno esito negativo con HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="58956-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="58956-117">Indica che l'allocazione è essenziale per l'esecuzione dell'attività che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="58956-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="58956-118">Se non è possibile allocare memoria, CLR non può garantire che l'attività possa essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="58956-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="58956-119">In caso di errore, CLR genera un oggetto <xref:System.Threading.ThreadAbortException> nel thread del sistema operativo fisico.</span><span class="sxs-lookup"><span data-stu-id="58956-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58956-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58956-120">Remarks</span></span>  
 <span data-ttu-id="58956-121">I metodi di allocazione della memoria definiti nelle interfacce [IHostMemoryManager](ihostmemorymanager-interface.md) e [IHostMalloc](ihostmalloc-interface.md) accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="58956-121">The memory allocation methods defined in the [IHostMemoryManager](ihostmemorymanager-interface.md) and [IHostMAlloc](ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="58956-122">A seconda del livello di gravità di un errore, un host può decidere se interrompere immediatamente la richiesta di allocazione o attendere fino a quando non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="58956-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58956-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58956-123">Requirements</span></span>  
 <span data-ttu-id="58956-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58956-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58956-125">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="58956-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58956-126">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58956-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58956-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58956-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58956-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58956-128">See also</span></span>

- [<span data-ttu-id="58956-129">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="58956-129">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="58956-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="58956-130">Hosting Enumerations</span></span>](hosting-enumerations.md)
