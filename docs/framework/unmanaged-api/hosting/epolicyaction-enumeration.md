---
title: Enumerazione EPolicyAction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f2c3a4138adfa354de07bc6df4e51d7697598b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="036fb-102">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="036fb-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="036fb-103">Descrive le azioni dei criteri dell'host è possibile impostare per le operazioni specificate da [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) e gli errori indicati da [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="036fb-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="036fb-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="036fb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="036fb-105">Members</span></span>  
  
|<span data-ttu-id="036fb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="036fb-106">Member</span></span>|<span data-ttu-id="036fb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="036fb-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="036fb-108">Specifica che common language runtime (CLR) deve interrompere il thread normalmente.</span><span class="sxs-lookup"><span data-stu-id="036fb-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="036fb-109">Interruzione di una normale include i tentativi di eseguire tutti `finally` si blocca, qualsiasi `catch` i blocchi correlati alle interruzioni del thread e i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="036fb-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="036fb-110">Specifica che Common Language Runtime deve essere stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="036fb-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="036fb-111">Senza ulteriore codice gestito può essere eseguito nel processo interessato, e i thread sono bloccati da rientrano nel CLR.</span><span class="sxs-lookup"><span data-stu-id="036fb-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="036fb-112">Specifica che Common Language Runtime deve tentare una valida uscita del processo, eseguendo i finalizzatori e l'esecuzione di operazioni di registrazione e di pulizia.</span><span class="sxs-lookup"><span data-stu-id="036fb-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="036fb-113">Specifica che Common Language Runtime si chiude il processo immediatamente, senza l'esecuzione dei finalizzatori o esecuzione di operazioni di registrazione e di pulizia.</span><span class="sxs-lookup"><span data-stu-id="036fb-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="036fb-114">Nowever, notifica viene inviata al debugger.</span><span class="sxs-lookup"><span data-stu-id="036fb-114">Nowever, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="036fb-115">Specifica che deve essere eseguita alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="036fb-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="036fb-116">Specifica che Common Language Runtime deve eseguire un'interruzione del thread in modo irregolare.</span><span class="sxs-lookup"><span data-stu-id="036fb-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="036fb-117">Solo quelli `catch` e `finally` blocchi contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="036fb-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="036fb-118">Specifica che Common Language Runtime deve uscire dal processo senza esecuzione dei finalizzatori o operazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="036fb-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="036fb-119">Specifica che Common Language Runtime deve eseguire uno scaricamento non regolare del <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="036fb-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="036fb-120">Solo i finalizzatori contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="036fb-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="036fb-121">Allo stesso modo, tutti i thread con questo <xref:System.AppDomain> nei relativi stack ricevere un `ThreadAbortException`, ma solo quelle `catch` e `finally` blocchi contrassegnati con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="036fb-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="036fb-122">Specifica che deve essere generata un'eccezione appropriata alla condizione, ad esempio di memoria insufficiente, overflow del buffer e così via.</span><span class="sxs-lookup"><span data-stu-id="036fb-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="036fb-123">Specifica che il <xref:System.AppDomain> deve essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="036fb-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="036fb-124">Common Language Runtime tenta di eseguire i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="036fb-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="036fb-125">Note</span><span class="sxs-lookup"><span data-stu-id="036fb-125">Remarks</span></span>  
 <span data-ttu-id="036fb-126">L'host imposta le azioni dei criteri chiamando i metodi del [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="036fb-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="036fb-127">Per informazioni sulle interruzioni regolari e irregolari, vedere il [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="036fb-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="036fb-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="036fb-128">Requirements</span></span>  
 <span data-ttu-id="036fb-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="036fb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="036fb-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="036fb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="036fb-131">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="036fb-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="036fb-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="036fb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036fb-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="036fb-133">See Also</span></span>  
 [<span data-ttu-id="036fb-134">EClrFailure (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="036fb-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="036fb-135">ICLRPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="036fb-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="036fb-136">IHostPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="036fb-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="036fb-137">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="036fb-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
