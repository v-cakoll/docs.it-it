---
title: Enumerazione EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d5f24d7415ff7ecceba6b0a5fbd3098d70dcd0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796019"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="54f75-102">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="54f75-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="54f75-103">Descrive il set di operazioni per il quale un host è possibile applicare azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="54f75-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54f75-104">Syntax</span></span>  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="54f75-105">Membri</span><span class="sxs-lookup"><span data-stu-id="54f75-105">Members</span></span>  
  
|<span data-ttu-id="54f75-106">Member</span><span class="sxs-lookup"><span data-stu-id="54f75-106">Member</span></span>|<span data-ttu-id="54f75-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54f75-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="54f75-108">L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato in modo non regolare (non applicabili).</span><span class="sxs-lookup"><span data-stu-id="54f75-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="54f75-109">L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="54f75-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="54f75-110">L'host può specificare azioni dei criteri da eseguire quando esegue i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="54f75-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="54f75-111">L'host può specificare le azioni dei criteri da eseguire quando il processo viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="54f75-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="54f75-112">L'host può specificare le azioni dei criteri da eseguire quando un thread viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="54f75-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="54f75-113">L'host può specificare le azioni dei criteri da eseguire quando si verifica un'interruzione del thread non applicabili in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="54f75-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="54f75-114">L'host può specificare criteri le azioni da intraprendere quando si verifica un'interruzione del thread non applicabili in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="54f75-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f75-115">Note</span><span class="sxs-lookup"><span data-stu-id="54f75-115">Remarks</span></span>  
 <span data-ttu-id="54f75-116">L'infrastruttura di affidabilità di common language runtime (CLR) distingue tra risorse e le interruzioni di errori di allocazione che si verificano nelle aree critiche di codice e quelli che si verificano in aree non critici del codice.</span><span class="sxs-lookup"><span data-stu-id="54f75-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="54f75-117">Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda di dove si verifica un errore nel codice.</span><span class="sxs-lookup"><span data-stu-id="54f75-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="54f75-118">Oggetto *area critica del codice* qualsiasi spazio in cui CLR non può garantire che l'interruzione di un'attività o riesce a completare una richiesta di risorse influirà solo l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="54f75-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="54f75-119">Ad esempio, se un'attività è bloccata da un blocco e riceve un valore HRESULT indicante un errore durante l'inoltro di una richiesta di allocazione della memoria, è sufficiente semplicemente interrompere l'attività per garantire la stabilità del <xref:System.AppDomain>, in quanto il <xref:System.AppDomain> potrebbe contenere altri attività in attesa per lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="54f75-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="54f75-120">Abbandonare corrente attività potrebbe causare altre attività di blocco (o un blocco) per un periodo illimitato.</span><span class="sxs-lookup"><span data-stu-id="54f75-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="54f75-121">In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> invece di instabilità potenziali rischi.</span><span class="sxs-lookup"><span data-stu-id="54f75-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="54f75-122">Oggetto *area critica del codice*, d'altra parte, è un'area in cui CLR è in grado di garantire che un'interruzione o un errore interesserà solo l'attività su cui si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="54f75-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="54f75-123">CLR consente di distinguere anche tra interruzioni (non applicabili) normali e non normali.</span><span class="sxs-lookup"><span data-stu-id="54f75-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="54f75-124">In generale, un'interruzione normali o irregolari si impegna per eseguire routine di gestione delle eccezioni e i finalizzatori prima dell'interruzione di un'attività, anche se questo tipo garantisce in alcun modo di un'interruzione non applicabili.</span><span class="sxs-lookup"><span data-stu-id="54f75-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f75-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54f75-125">Requirements</span></span>  
 <span data-ttu-id="54f75-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54f75-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f75-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54f75-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54f75-128">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54f75-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54f75-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f75-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f75-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f75-130">See also</span></span>

- [<span data-ttu-id="54f75-131">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="54f75-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="54f75-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="54f75-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="54f75-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="54f75-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="54f75-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="54f75-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="54f75-135">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="54f75-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
