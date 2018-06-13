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
ms.openlocfilehash: acf4f3f582e417c5e7b814622986427f996796ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432527"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="42282-102">Enumerazione EMemoryCriticalLevel</span><span class="sxs-lookup"><span data-stu-id="42282-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="42282-103">Contiene valori che indicano l'impatto di un errore quando un'allocazione di memoria specifico è stato richiesto ma non può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="42282-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42282-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42282-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="42282-105">Membri</span><span class="sxs-lookup"><span data-stu-id="42282-105">Members</span></span>  
  
|<span data-ttu-id="42282-106">Membro</span><span class="sxs-lookup"><span data-stu-id="42282-106">Member</span></span>|<span data-ttu-id="42282-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42282-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="42282-108">Indica che l'allocazione è critica per l'esecuzione di codice gestito nel dominio che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="42282-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="42282-109">Se la memoria non può essere allocata, Common Language Runtime non garantisce che il dominio è ancora utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="42282-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="42282-110">L'host decide l'azione da intraprendere quando non è possibile soddisfare l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="42282-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="42282-111">È possibile indicare a CLR di interrompere il `AppDomain` , automaticamente o consentire di continuare l'esecuzione chiamando metodi sulla [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42282-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="42282-112">Indica che l'allocazione è fondamentale per l'esecuzione di codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="42282-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="42282-113">Questo valore viene utilizzato durante l'avvio e durante l'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="42282-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="42282-114">Se la memoria non può essere allocata, Common Language Runtime non può operare nel processo.</span><span class="sxs-lookup"><span data-stu-id="42282-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="42282-115">Se l'allocazione ha esito negativo, CLR è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="42282-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="42282-116">Tutte le chiamate successive a CLR esito negativo con HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42282-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="42282-117">Indica che l'allocazione è fondamentale per l'esecuzione dell'attività che ha richiesto l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="42282-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="42282-118">Se la memoria non può essere allocata, Common Language Runtime non garantisce che l'attività può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="42282-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="42282-119">In caso di errore, CLR genera un <xref:System.Threading.ThreadAbortException> sul thread del sistema operazione fisica.</span><span class="sxs-lookup"><span data-stu-id="42282-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42282-120">Note</span><span class="sxs-lookup"><span data-stu-id="42282-120">Remarks</span></span>  
 <span data-ttu-id="42282-121">I metodi di allocazione di memoria definiti nel [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) e [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfacce accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="42282-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="42282-122">In base alla gravità dell'errore, un host può decidere se eseguire immediatamente la richiesta di allocazione o attendere finché può essere soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="42282-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42282-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42282-123">Requirements</span></span>  
 <span data-ttu-id="42282-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42282-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42282-125">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="42282-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42282-126">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="42282-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42282-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42282-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42282-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42282-128">See Also</span></span>  
 [<span data-ttu-id="42282-129">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="42282-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="42282-130">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="42282-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
