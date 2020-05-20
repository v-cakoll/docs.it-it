---
title: Enumerazione EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 8788d6e2220778a3f0926d5ed3dd59142487bcca
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616190"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="7d8ed-102">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="7d8ed-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="7d8ed-103">Descrive le azioni dei criteri che l'host può impostare per le operazioni descritte da [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) ed errori descritti da [EClrFailure](eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7d8ed-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d8ed-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="7d8ed-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7d8ed-105">Members</span></span>  
  
|<span data-ttu-id="7d8ed-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7d8ed-106">Member</span></span>|<span data-ttu-id="7d8ed-107">Description</span><span class="sxs-lookup"><span data-stu-id="7d8ed-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="7d8ed-108">Specifica che il Common Language Runtime (CLR) deve interrompere normalmente il thread.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="7d8ed-109">Un'interruzione normale include i tentativi di eseguire tutti i `finally` blocchi, i `catch` blocchi correlati a interruzioni di thread e i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="7d8ed-110">Specifica che CLR deve immettere uno stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="7d8ed-111">Non è possibile eseguire ulteriori codice gestito nel processo interessato e i thread non possono accedere a CLR.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="7d8ed-112">Specifica che CLR deve tentare un'uscita normale del processo, tra cui l'esecuzione di finalizzatori e l'esecuzione di operazioni di pulizia e registrazione.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="7d8ed-113">Specifica che CLR deve uscire immediatamente dal processo, senza eseguire finalizzatori o eseguire operazioni di pulizia e registrazione.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="7d8ed-114">Tuttavia, la notifica viene inviata al debugger.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="7d8ed-115">Specifica che non deve essere eseguita alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="7d8ed-116">Specifica che CLR deve eseguire un'interruzione di thread scortese.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="7d8ed-117">`catch` `finally` Vengono eseguiti solo i blocchi e contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="7d8ed-118">Specifica che CLR deve uscire dal processo senza eseguire finalizzatori o operazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="7d8ed-119">Specifica che CLR deve eseguire uno scaricamento rude di <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="7d8ed-120">Vengono eseguiti solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="7d8ed-121">Analogamente, tutti i thread con questo <xref:System.AppDomain> nello stack ricevono un oggetto `ThreadAbortException` , ma `catch` `finally` vengono eseguiti solo i blocchi e contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="7d8ed-122">Specifica che deve essere generata un'eccezione appropriata per la condizione, ad esempio memoria insufficiente, overflow del buffer e così via.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="7d8ed-123">Specifica che <xref:System.AppDomain> deve essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="7d8ed-124">CLR tenta di eseguire i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="7d8ed-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d8ed-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7d8ed-125">Remarks</span></span>  
 <span data-ttu-id="7d8ed-126">L'host imposta le azioni dei criteri chiamando i metodi dell'interfaccia [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="7d8ed-127">Per informazioni sulle interruzioni scortesi e aggraziate, vedere l'enumerazione [EClrOperation](eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="7d8ed-127">For information about rude and graceful aborts, see the [EClrOperation](eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8ed-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d8ed-128">Requirements</span></span>  
 <span data-ttu-id="7d8ed-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d8ed-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8ed-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7d8ed-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d8ed-131">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d8ed-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d8ed-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8ed-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8ed-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d8ed-133">See also</span></span>

- [<span data-ttu-id="7d8ed-134">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="7d8ed-134">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="7d8ed-135">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7d8ed-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="7d8ed-136">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="7d8ed-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="7d8ed-137">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="7d8ed-137">Hosting Enumerations</span></span>](hosting-enumerations.md)
