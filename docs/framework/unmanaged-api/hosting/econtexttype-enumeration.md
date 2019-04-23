---
title: Enumerazione EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3643bf4880532a46fe7f9f57b8077032013728
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118079"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="d582a-102">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="d582a-102">EContextType Enumeration</span></span>
<span data-ttu-id="d582a-103">Descrive il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d582a-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d582a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d582a-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="d582a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d582a-105">Members</span></span>  
  
|<span data-ttu-id="d582a-106">Member</span><span class="sxs-lookup"><span data-stu-id="d582a-106">Member</span></span>|<span data-ttu-id="d582a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d582a-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="d582a-108">Indica il contesto sul thread corrente in fase di common language runtime (CLR) chiama il [IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) metodo o il contesto di richiesta da parte di CLR in una chiamata al [ IHostSecurityManager:: SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d582a-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="d582a-109">Indica un contesto in cui l'host dispone di privilegi più bassi, ad esempio il garbage collector, o i costruttori di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="d582a-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d582a-110">Note</span><span class="sxs-lookup"><span data-stu-id="d582a-110">Remarks</span></span>  
 <span data-ttu-id="d582a-111">CLR fornisce uno dei `EContextType` i valori come un valore di parametro nelle chiamate al `IHostSecurityManager::GetSecurityContext` e `IHostSecurityManager::SetSecurityContext` metodi.</span><span class="sxs-lookup"><span data-stu-id="d582a-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d582a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d582a-112">Requirements</span></span>  
 <span data-ttu-id="d582a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d582a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d582a-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d582a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d582a-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d582a-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d582a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d582a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d582a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d582a-117">See also</span></span>

- [<span data-ttu-id="d582a-118">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="d582a-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d582a-119">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="d582a-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="d582a-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d582a-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
