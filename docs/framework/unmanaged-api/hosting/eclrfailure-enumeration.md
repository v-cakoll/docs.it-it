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
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131116"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="60c3f-102">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="60c3f-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="60c3f-103">Descrive il set di errori per i quali un host può impostare le azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="60c3f-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60c3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60c3f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="60c3f-105">Members</span><span class="sxs-lookup"><span data-stu-id="60c3f-105">Members</span></span>  
  
|<span data-ttu-id="60c3f-106">Member</span><span class="sxs-lookup"><span data-stu-id="60c3f-106">Member</span></span>|<span data-ttu-id="60c3f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60c3f-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="60c3f-108">Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area di codice non critica.</span><span class="sxs-lookup"><span data-stu-id="60c3f-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="60c3f-109">Si è verificato un errore durante il tentativo di allocare una risorsa, ad esempio un thread, un blocco di memoria o un blocco, in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="60c3f-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="60c3f-110">Il Common Language Runtime (CLR) non è più in grado di eseguire il codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="60c3f-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="60c3f-111">In questo caso, le chiamate a qualsiasi funzione di hosting restituiscono un valore HRESULT di HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60c3f-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="60c3f-112">Un thread non è riuscito a rilasciare un blocco quando viene restituito da un oggetto <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="60c3f-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="60c3f-113">L'host non è in grado di impostare questo errore in modo da causare l'interruzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="60c3f-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="60c3f-114">Si è verificato un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="60c3f-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="60c3f-115">È stato effettuato un tentativo di lettura o scrittura della memoria protetta.</span><span class="sxs-lookup"><span data-stu-id="60c3f-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="60c3f-116">Non supportato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="60c3f-116">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="60c3f-117">Si è verificato un errore del contratto di codice.</span><span class="sxs-lookup"><span data-stu-id="60c3f-117">A code contract failure occurred.</span></span> <span data-ttu-id="60c3f-118">Vedere [contratti di codice](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="60c3f-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60c3f-119">Note</span><span class="sxs-lookup"><span data-stu-id="60c3f-119">Remarks</span></span>  
 <span data-ttu-id="60c3f-120">Vedere il metodo [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) per un elenco di valori [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) che l'host può usare per specificare le azioni dei criteri per le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="60c3f-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="60c3f-121">Per ulteriori informazioni sulle aree di codice critiche e non critiche, vedere [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="60c3f-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c3f-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60c3f-122">Requirements</span></span>  
 <span data-ttu-id="60c3f-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60c3f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c3f-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60c3f-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60c3f-125">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="60c3f-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60c3f-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c3f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c3f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60c3f-127">See also</span></span>

- [<span data-ttu-id="60c3f-128">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="60c3f-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="60c3f-129">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="60c3f-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="60c3f-130">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="60c3f-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="60c3f-131">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="60c3f-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
