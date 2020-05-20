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
ms.openlocfilehash: e7cb1c2070e760258e548d2f45e3b6ed11e046c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616320"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="ca5b3-102">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="ca5b3-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="ca5b3-103">Descrive il set di operazioni per cui un host può applicare le azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca5b3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="ca5b3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ca5b3-105">Members</span></span>  
  
|<span data-ttu-id="ca5b3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ca5b3-106">Member</span></span>|<span data-ttu-id="ca5b3-107">Description</span><span class="sxs-lookup"><span data-stu-id="ca5b3-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="ca5b3-108">L'host può specificare le azioni dei criteri da intraprendere quando un oggetto <xref:System.AppDomain> viene scaricato in modo non normale (rude).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="ca5b3-109">L'host può specificare le azioni dei criteri da intraprendere quando <xref:System.AppDomain> viene scaricato un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="ca5b3-110">L'host può specificare le azioni dei criteri da intraprendere quando vengono eseguiti i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="ca5b3-111">L'host può specificare le azioni dei criteri da intraprendere quando il processo viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="ca5b3-112">L'host può specificare le azioni dei criteri da intraprendere quando un thread viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="ca5b3-113">L'host può specificare le azioni dei criteri da intraprendere quando si verifica un'interruzione di thread rude in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="ca5b3-114">L'host può specificare le azioni dei criteri da intraprendere quando si verifica un'interruzione di thread rude in un'area di codice non critica.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca5b3-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ca5b3-115">Remarks</span></span>  
 <span data-ttu-id="ca5b3-116">L'infrastruttura di affidabilità Common Language Runtime (CLR) distingue le interruzioni e gli errori di allocazione delle risorse che si verificano in aree critiche del codice e quelle che si verificano in aree di codice non critiche.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="ca5b3-117">Questa distinzione è progettata per consentire agli host di impostare criteri diversi a seconda della posizione in cui si verifica un errore nel codice.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="ca5b3-118">Un' *area critica del codice* è uno spazio in cui CLR non è in grado di garantire che l'interruzione di un'attività o la mancata esecuzione di una richiesta di risorse influirà solo sull'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="ca5b3-119">Se, ad esempio, un'attività mantiene un blocco e riceve un valore HRESULT che indica un errore durante l'esecuzione di una richiesta di allocazione della memoria, non è sufficiente interrompere tale attività per garantire la stabilità di <xref:System.AppDomain> , perché <xref:System.AppDomain> potrebbe contenere altre attività in attesa dello stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="ca5b3-120">Per abbandonare l'attività corrente, le altre attività potrebbero smettere di rispondere.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="ca5b3-121">In tal caso, l'host deve essere in grado di scaricare l'intero <xref:System.AppDomain> anziché il rischio di instabilità.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="ca5b3-122">Un' *area di codice non critica*, d'altra parte, è un'area in cui CLR può garantire che un'interruzione o un errore influirà solo sull'attività su cui si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="ca5b3-123">CLR distingue anche tra interruzioni aggraziate e non aggraziate (rude).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="ca5b3-124">In generale, un'interruzione normale o normale esegue ogni sforzo per eseguire le routine di gestione delle eccezioni e i finalizzatori prima di interrompere un'attività, mentre un'interruzione rude non rende tali garanzie.</span><span class="sxs-lookup"><span data-stu-id="ca5b3-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5b3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca5b3-125">Requirements</span></span>  
 <span data-ttu-id="ca5b3-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca5b3-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5b3-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca5b3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca5b3-128">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca5b3-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca5b3-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5b3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5b3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca5b3-130">See also</span></span>

- [<span data-ttu-id="ca5b3-131">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="ca5b3-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="ca5b3-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="ca5b3-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="ca5b3-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ca5b3-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="ca5b3-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ca5b3-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="ca5b3-135">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="ca5b3-135">Hosting Enumerations</span></span>](hosting-enumerations.md)
