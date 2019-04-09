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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19dacae05766566521f563d0d24980c01dfb7a0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144287"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="f09c9-102">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="f09c9-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="f09c9-103">Descrive il set di errori per il quale l'host può impostare le azioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="f09c9-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f09c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f09c9-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="f09c9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f09c9-105">Members</span></span>  
  
|<span data-ttu-id="f09c9-106">Member</span><span class="sxs-lookup"><span data-stu-id="f09c9-106">Member</span></span>|<span data-ttu-id="f09c9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f09c9-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="f09c9-108">Si è verificato un errore durante il tentativo di allocare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="f09c9-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="f09c9-109">Si è verificato un errore durante il tentativo di allocare una risorsa (ad esempio, un thread, un blocco di memoria o un blocco) in un'area critica del codice.</span><span class="sxs-lookup"><span data-stu-id="f09c9-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="f09c9-110">Common language runtime (CLR) non è più in grado di eseguire codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="f09c9-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="f09c9-111">Da questo momento, le chiamate a qualsiasi host funzioni restituiscono un valore HRESULT di HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f09c9-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="f09c9-112">Un thread non è riuscito a rilasciare un blocco all'uscita da un <xref:System.AppDomain> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f09c9-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="f09c9-113">L'host non è possibile impostare questo tentativo provoca l'interruzione di un thread.</span><span class="sxs-lookup"><span data-stu-id="f09c9-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="f09c9-114">Si è verificato un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="f09c9-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="f09c9-115">È stato effettuato un tentativo di leggere o scrivere nella memoria protetta.</span><span class="sxs-lookup"><span data-stu-id="f09c9-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="f09c9-116">Non supportato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f09c9-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="f09c9-117">Si è verificato un errore di contratto di codice.</span><span class="sxs-lookup"><span data-stu-id="f09c9-117">A code contract failure occurred.</span></span> <span data-ttu-id="f09c9-118">Visualizzare [contratti di codice](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="f09c9-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f09c9-119">Note</span><span class="sxs-lookup"><span data-stu-id="f09c9-119">Remarks</span></span>  
 <span data-ttu-id="f09c9-120">Vedere le [SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metodo per un elenco delle [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori host possono essere utilizzati per specificare le azioni dei criteri per le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="f09c9-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="f09c9-121">Per altre informazioni sulle aree critiche e non critici del codice, vedere [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f09c9-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f09c9-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f09c9-122">Requirements</span></span>  
 <span data-ttu-id="f09c9-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f09c9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f09c9-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f09c9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f09c9-125">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f09c9-125">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f09c9-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f09c9-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f09c9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f09c9-127">See also</span></span>

- [<span data-ttu-id="f09c9-128">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f09c9-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="f09c9-129">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="f09c9-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="f09c9-130">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f09c9-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="f09c9-131">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="f09c9-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
