---
title: Enumerazione EContextType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd068816c5a642a7a8230fc14045e3f43980936c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="04549-102">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="04549-102">EContextType Enumeration</span></span>
<span data-ttu-id="04549-103">Descrive il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04549-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04549-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04549-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="04549-105">Membri</span><span class="sxs-lookup"><span data-stu-id="04549-105">Members</span></span>  
  
|<span data-ttu-id="04549-106">Membro</span><span class="sxs-lookup"><span data-stu-id="04549-106">Member</span></span>|<span data-ttu-id="04549-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04549-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="04549-108">Indica il contesto sul thread corrente in fase di common language runtime (CLR) chiama il [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) metodo o il contesto di richiesta da parte di CLR in una chiamata al [ IHostSecurityManager:: SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="04549-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="04549-109">Indica un contesto in cui l'host dispone di privilegi più limitati, ad esempio, il garbage collector o costruttori di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="04549-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04549-110">Note</span><span class="sxs-lookup"><span data-stu-id="04549-110">Remarks</span></span>  
 <span data-ttu-id="04549-111">CLR fornisce uno del `EContextType` valori come valore di parametro nelle chiamate al `IHostSecurityManager::GetSecurityContext` e `IHostSecurityManager::SetSecurityContext` metodi.</span><span class="sxs-lookup"><span data-stu-id="04549-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04549-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04549-112">Requirements</span></span>  
 <span data-ttu-id="04549-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04549-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04549-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="04549-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04549-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04549-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04549-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04549-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04549-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04549-117">See Also</span></span>  
 [<span data-ttu-id="04549-118">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="04549-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="04549-119">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="04549-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="04549-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="04549-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
