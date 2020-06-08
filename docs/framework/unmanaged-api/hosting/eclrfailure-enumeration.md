---
title: Enumerazione EClrFailure
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: fa2b5052a1d569487f0c6c72699ff9ab571beefc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504394"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="aa5bb-102">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="aa5bb-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="aa5bb-103">Descrive il set di errori per i quali un host può impostare le azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa5bb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="aa5bb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="aa5bb-105">Members</span></span>  
  
|<span data-ttu-id="aa5bb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="aa5bb-106">Member</span></span>|<span data-ttu-id="aa5bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa5bb-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="aa5bb-108">Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area di codice non critica.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="aa5bb-109">Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="aa5bb-110">Il Common Language Runtime (CLR) non è più in grado di eseguire il codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="aa5bb-111">In questo caso, le chiamate a qualsiasi funzione di hosting restituiscono un valore HRESULT pari a HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="aa5bb-112">Un thread non è riuscito a rilasciare un blocco in seguito alla restituzione da un <xref:System.AppDomain> oggetto.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="aa5bb-113">L'host non è in grado di impostare questo errore in modo da causare l'interruzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="aa5bb-114">Si è verificato un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="aa5bb-115">È stato effettuato un tentativo di lettura o scrittura della memoria protetta.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="aa5bb-116">Non supportato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="aa5bb-117">Si è verificato un errore del contratto di codice.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-117">A code contract failure occurred.</span></span> <span data-ttu-id="aa5bb-118">Vedere [contratti di codice](../../debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="aa5bb-118">See [Code Contracts](../../debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa5bb-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="aa5bb-119">Remarks</span></span>  
 <span data-ttu-id="aa5bb-120">Vedere il metodo [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) per un elenco di valori [EPolicyAction](epolicyaction-enumeration.md) che l'host può usare per specificare le azioni dei criteri per le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="aa5bb-120">See the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="aa5bb-121">Per ulteriori informazioni sulle aree di codice critiche e non critiche, vedere [EClrOperation](eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="aa5bb-121">For more information about critical and non-critical regions of code, see [EClrOperation](eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa5bb-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa5bb-122">Requirements</span></span>  
 <span data-ttu-id="aa5bb-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa5bb-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa5bb-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aa5bb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa5bb-125">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa5bb-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa5bb-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa5bb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa5bb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa5bb-127">See also</span></span>

- [<span data-ttu-id="aa5bb-128">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="aa5bb-128">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="aa5bb-129">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="aa5bb-129">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="aa5bb-130">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="aa5bb-130">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="aa5bb-131">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="aa5bb-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
