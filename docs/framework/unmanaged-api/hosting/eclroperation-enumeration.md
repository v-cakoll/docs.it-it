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
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434245"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="6b176-102">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="6b176-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="6b176-103">Viene descritto il set di operazioni per il quale un host può applicare le azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="6b176-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b176-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b176-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6b176-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6b176-105">Members</span></span>  
  
|<span data-ttu-id="6b176-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6b176-106">Member</span></span>|<span data-ttu-id="6b176-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b176-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="6b176-108">L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato in un non normale modo.</span><span class="sxs-lookup"><span data-stu-id="6b176-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="6b176-109">L'host può specificare le azioni dei criteri da eseguire quando un <xref:System.AppDomain> viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="6b176-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="6b176-110">L'host può specificare le azioni da intraprendere quando esegue i finalizzatori dei criteri.</span><span class="sxs-lookup"><span data-stu-id="6b176-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="6b176-111">L'host può specificare le azioni dei criteri da eseguire quando il processo viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="6b176-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="6b176-112">L'host può specificare le azioni dei criteri da eseguire quando un thread viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="6b176-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="6b176-113">L'host può specificare le azioni da intraprendere quando si verifica un'interruzione del thread in modo irregolare in un'area critica del codice dei criteri.</span><span class="sxs-lookup"><span data-stu-id="6b176-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="6b176-114">L'host può specificare le azioni dei criteri da eseguire quando si verifica un'interruzione del thread in modo irregolare in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="6b176-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b176-115">Note</span><span class="sxs-lookup"><span data-stu-id="6b176-115">Remarks</span></span>  
 <span data-ttu-id="6b176-116">L'infrastruttura di affidabilità di common language runtime (CLR) viene fatta distinzione tra le interruzioni e risorse errori di allocazione che si verificano in aree critiche del codice e quelli che si verificano in aree non critici del codice.</span><span class="sxs-lookup"><span data-stu-id="6b176-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="6b176-117">Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda di dove si verifica un errore nel codice.</span><span class="sxs-lookup"><span data-stu-id="6b176-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="6b176-118">Oggetto *area critica del codice* è qualsiasi spazio in Common Language Runtime non è possibile garantire che l'interruzione di un'attività o il mancato completamento di una richiesta di risorse influirà solo l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="6b176-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="6b176-119">Ad esempio, se un'attività contenente un blocco e riceve un HRESULT che indica un errore durante l'inoltro di una richiesta di allocazione della memoria, è sufficiente semplicemente interrompere l'attività per garantire la stabilità del <xref:System.AppDomain>, in quanto il <xref:System.AppDomain> potrebbe contenere altri attività in attesa del blocco stesso.</span><span class="sxs-lookup"><span data-stu-id="6b176-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="6b176-120">Abbandono corrente attività potrebbe causare altre attività di blocco (o di blocco) per un periodo illimitato.</span><span class="sxs-lookup"><span data-stu-id="6b176-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="6b176-121">In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> anziché instabilità a rischio.</span><span class="sxs-lookup"><span data-stu-id="6b176-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="6b176-122">Oggetto *area critica di codice*, d'altra parte, è un'area in cui il CLR è in grado di garantire che un'interruzione o un errore influirà solo l'attività che si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="6b176-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="6b176-123">Common Language Runtime distingue anche tra normale e non regolari interruzioni (RudeAbort).</span><span class="sxs-lookup"><span data-stu-id="6b176-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="6b176-124">In generale, interruzione di una normale o normale cercherà di eseguire routine di gestione delle eccezioni e finalizzatori prima di annullare un'attività, mentre un'interruzione irregolare alcuna garanzia di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="6b176-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b176-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b176-125">Requirements</span></span>  
 <span data-ttu-id="6b176-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b176-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b176-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6b176-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b176-128">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6b176-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b176-129">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b176-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b176-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b176-130">See Also</span></span>  
 [<span data-ttu-id="6b176-131">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="6b176-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="6b176-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="6b176-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="6b176-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6b176-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="6b176-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6b176-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="6b176-135">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="6b176-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
