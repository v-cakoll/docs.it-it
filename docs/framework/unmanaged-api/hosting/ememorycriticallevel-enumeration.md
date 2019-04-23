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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122291"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="89c7d-102">Enumerazione EMemoryCriticalLevel</span><span class="sxs-lookup"><span data-stu-id="89c7d-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="89c7d-103">Contiene valori che indicano l'impatto di un errore quando un'allocazione di memoria specifico è stato richiesto ma non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="89c7d-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89c7d-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="89c7d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="89c7d-105">Members</span></span>  
  
|<span data-ttu-id="89c7d-106">Member</span><span class="sxs-lookup"><span data-stu-id="89c7d-106">Member</span></span>|<span data-ttu-id="89c7d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89c7d-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="89c7d-108">Indica che l'allocazione è fondamentale per l'esecuzione di codice gestito nel dominio che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="89c7d-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="89c7d-109">Se non è possibile allocare memoria, CLR non può garantire che il dominio è ancora utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="89c7d-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="89c7d-110">L'host decide l'azione da intraprendere quando l'allocazione non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="89c7d-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="89c7d-111">È possibile indicare a CLR per interrompere la `AppDomain` automaticamente, oppure consentire di continuare l'esecuzione chiamando metodi sulla [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="89c7d-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="89c7d-112">Indica che l'allocazione è fondamentale per l'esecuzione di codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="89c7d-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="89c7d-113">Questo valore viene utilizzato durante l'avvio e durante l'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="89c7d-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="89c7d-114">Se non è possibile allocare memoria, CLR non può funzionare nel processo.</span><span class="sxs-lookup"><span data-stu-id="89c7d-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="89c7d-115">Se l'allocazione ha esito negativo, il CLR è disabilitato in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="89c7d-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="89c7d-116">Tutte le chiamate successive in CLR non HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89c7d-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="89c7d-117">Indica che l'allocazione è fondamentale per l'esecuzione di attività che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="89c7d-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="89c7d-118">Se non è possibile allocare memoria, CLR non può garantire che l'attività possa essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="89c7d-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="89c7d-119">In caso di errore, il Common Language Runtime genera una <xref:System.Threading.ThreadAbortException> sul thread del sistema operativo fisico.</span><span class="sxs-lookup"><span data-stu-id="89c7d-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89c7d-120">Note</span><span class="sxs-lookup"><span data-stu-id="89c7d-120">Remarks</span></span>  
 <span data-ttu-id="89c7d-121">I metodi di allocazione di memoria definiti nel [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) e [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfacce accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="89c7d-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="89c7d-122">In base alla gravità dell'errore, un host può decidere se eseguire immediatamente la richiesta di allocazione o in attesa finché può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="89c7d-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c7d-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89c7d-123">Requirements</span></span>  
 <span data-ttu-id="89c7d-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89c7d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c7d-125">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89c7d-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89c7d-126">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89c7d-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89c7d-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c7d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c7d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89c7d-128">See also</span></span>

- [<span data-ttu-id="89c7d-129">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="89c7d-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="89c7d-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="89c7d-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
