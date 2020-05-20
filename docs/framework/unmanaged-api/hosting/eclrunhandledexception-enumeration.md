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
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616307"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="236ba-102">Enumerazione EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="236ba-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="236ba-103">Descrive le opzioni disponibili per la gestione delle eccezioni non gestite nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="236ba-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="236ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="236ba-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="236ba-105">Membri</span><span class="sxs-lookup"><span data-stu-id="236ba-105">Members</span></span>  
  
|<span data-ttu-id="236ba-106">Membro</span><span class="sxs-lookup"><span data-stu-id="236ba-106">Member</span></span>|<span data-ttu-id="236ba-107">Description</span><span class="sxs-lookup"><span data-stu-id="236ba-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="236ba-108">Specifica che si verifica il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="236ba-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="236ba-109">Il processo è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="236ba-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="236ba-110">Specifica che il Common Language Runtime (CLR) ignora le eccezioni non gestite e consente all'host di determinare eventuali ulteriori azioni.</span><span class="sxs-lookup"><span data-stu-id="236ba-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="236ba-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="236ba-111">Remarks</span></span>  
 <span data-ttu-id="236ba-112">Per specificare che CLR si comporti come le versioni precedenti, utilizzare il `eHostDeterminedPolicy` membro.</span><span class="sxs-lookup"><span data-stu-id="236ba-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="236ba-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="236ba-113">Requirements</span></span>  
 <span data-ttu-id="236ba-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="236ba-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="236ba-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="236ba-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="236ba-116">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="236ba-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="236ba-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="236ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="236ba-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="236ba-118">See also</span></span>

- [<span data-ttu-id="236ba-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="236ba-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="236ba-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="236ba-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="236ba-121">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="236ba-121">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="236ba-122">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="236ba-122">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="236ba-123">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="236ba-123">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="236ba-124">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="236ba-124">Hosting Enumerations</span></span>](hosting-enumerations.md)
