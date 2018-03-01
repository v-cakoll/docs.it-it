---
title: Enumerazione EClrUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8fcc9254499724d94153c445943fdaf78d12a10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="a2d58-102">Enumerazione EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="a2d58-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="a2d58-103">Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="a2d58-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2d58-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="a2d58-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a2d58-105">Members</span></span>  
  
|<span data-ttu-id="a2d58-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a2d58-106">Member</span></span>|<span data-ttu-id="a2d58-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d58-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="a2d58-108">Specifica che si verifica il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="a2d58-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="a2d58-109">Il processo viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="a2d58-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="a2d58-110">Specifica che common language runtime (CLR) ignora le eccezioni non gestite e consente all'host di determinare alcuna azione ulteriore.</span><span class="sxs-lookup"><span data-stu-id="a2d58-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2d58-111">Note</span><span class="sxs-lookup"><span data-stu-id="a2d58-111">Remarks</span></span>  
 <span data-ttu-id="a2d58-112">Per specificare che CLR si comportano come le versioni precedenti, usare il `eHostDeterminedPolicy` membro.</span><span class="sxs-lookup"><span data-stu-id="a2d58-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2d58-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2d58-113">Requirements</span></span>  
 <span data-ttu-id="a2d58-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2d58-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d58-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a2d58-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2d58-116">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2d58-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2d58-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2d58-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d58-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2d58-118">See Also</span></span>  
 [<span data-ttu-id="a2d58-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="a2d58-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="a2d58-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="a2d58-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="a2d58-121">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a2d58-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="a2d58-122">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="a2d58-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [<span data-ttu-id="a2d58-123">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a2d58-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="a2d58-124">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a2d58-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
