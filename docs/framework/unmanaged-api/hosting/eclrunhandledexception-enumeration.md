---
title: Enumerazione EClrUnhandledException
ms.date: 03/30/2017
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
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131243"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="40937-102">Enumerazione EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="40937-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="40937-103">Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="40937-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40937-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40937-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="40937-105">Members</span><span class="sxs-lookup"><span data-stu-id="40937-105">Members</span></span>  
  
|<span data-ttu-id="40937-106">Member</span><span class="sxs-lookup"><span data-stu-id="40937-106">Member</span></span>|<span data-ttu-id="40937-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40937-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="40937-108">Specifica che si verifica il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="40937-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="40937-109">Il processo è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="40937-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="40937-110">Specifica che il Common Language Runtime (CLR) ignora le eccezioni non gestite e consente all'host di determinare eventuali ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="40937-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40937-111">Note</span><span class="sxs-lookup"><span data-stu-id="40937-111">Remarks</span></span>  
 <span data-ttu-id="40937-112">Per specificare che CLR si comporti come le versioni precedenti, usare il membro `eHostDeterminedPolicy`.</span><span class="sxs-lookup"><span data-stu-id="40937-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40937-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40937-113">Requirements</span></span>  
 <span data-ttu-id="40937-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40937-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40937-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40937-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40937-116">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40937-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40937-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40937-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40937-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40937-118">See also</span></span>

- [<span data-ttu-id="40937-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="40937-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="40937-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="40937-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="40937-121">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="40937-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="40937-122">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="40937-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="40937-123">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="40937-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="40937-124">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="40937-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
