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
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138236"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="dc33a-102">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="dc33a-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="dc33a-103">Descrive le azioni dei criteri che l'host può impostare per le operazioni descritte da [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) ed errori descritti da [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="dc33a-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc33a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc33a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="dc33a-105">Members</span><span class="sxs-lookup"><span data-stu-id="dc33a-105">Members</span></span>  
  
|<span data-ttu-id="dc33a-106">Member</span><span class="sxs-lookup"><span data-stu-id="dc33a-106">Member</span></span>|<span data-ttu-id="dc33a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc33a-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="dc33a-108">Specifica che il Common Language Runtime (CLR) deve interrompere normalmente il thread.</span><span class="sxs-lookup"><span data-stu-id="dc33a-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="dc33a-109">Un'interruzione normale include i tentativi di esecuzione di tutti i blocchi di `finally`, di eventuali blocchi `catch` correlati a interruzioni di thread e finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="dc33a-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="dc33a-110">Specifica che CLR deve immettere uno stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="dc33a-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="dc33a-111">Non è possibile eseguire ulteriori codice gestito nel processo interessato e i thread non possono accedere a CLR.</span><span class="sxs-lookup"><span data-stu-id="dc33a-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="dc33a-112">Specifica che CLR deve tentare un'uscita normale del processo, tra cui l'esecuzione di finalizzatori e l'esecuzione di operazioni di pulizia e registrazione.</span><span class="sxs-lookup"><span data-stu-id="dc33a-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="dc33a-113">Specifica che CLR deve uscire immediatamente dal processo, senza eseguire finalizzatori o eseguire operazioni di pulizia e registrazione.</span><span class="sxs-lookup"><span data-stu-id="dc33a-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="dc33a-114">Tuttavia, la notifica viene inviata al debugger.</span><span class="sxs-lookup"><span data-stu-id="dc33a-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="dc33a-115">Specifica che non deve essere eseguita alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="dc33a-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="dc33a-116">Specifica che CLR deve eseguire un'interruzione di thread scortese.</span><span class="sxs-lookup"><span data-stu-id="dc33a-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="dc33a-117">Vengono eseguiti solo i blocchi `catch` e `finally` contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dc33a-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="dc33a-118">Specifica che CLR deve uscire dal processo senza eseguire finalizzatori o operazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="dc33a-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="dc33a-119">Specifica che CLR deve eseguire uno scaricamento rude del <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="dc33a-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="dc33a-120">Vengono eseguiti solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dc33a-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="dc33a-121">Analogamente, tutti i thread con questo <xref:System.AppDomain> nello stack ricevono una `ThreadAbortException`, ma vengono eseguiti solo i blocchi `catch` e `finally` contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dc33a-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="dc33a-122">Specifica che deve essere generata un'eccezione appropriata per la condizione, ad esempio memoria insufficiente, overflow del buffer e così via.</span><span class="sxs-lookup"><span data-stu-id="dc33a-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="dc33a-123">Specifica che il <xref:System.AppDomain> deve essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="dc33a-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="dc33a-124">CLR tenta di eseguire i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="dc33a-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc33a-125">Note</span><span class="sxs-lookup"><span data-stu-id="dc33a-125">Remarks</span></span>  
 <span data-ttu-id="dc33a-126">L'host imposta le azioni dei criteri chiamando i metodi dell'interfaccia [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dc33a-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="dc33a-127">Per informazioni sulle interruzioni scortesi e aggraziate, vedere l'enumerazione [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="dc33a-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc33a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc33a-128">Requirements</span></span>  
 <span data-ttu-id="dc33a-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc33a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc33a-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc33a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc33a-131">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc33a-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc33a-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc33a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc33a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc33a-133">See also</span></span>

- [<span data-ttu-id="dc33a-134">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="dc33a-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="dc33a-135">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="dc33a-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="dc33a-136">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="dc33a-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="dc33a-137">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="dc33a-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
