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
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131149"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="4fcfb-102">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="4fcfb-102">EContextType Enumeration</span></span>
<span data-ttu-id="4fcfb-103">Descrive il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fcfb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fcfb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="4fcfb-105">Members</span><span class="sxs-lookup"><span data-stu-id="4fcfb-105">Members</span></span>  
  
|<span data-ttu-id="4fcfb-106">Member</span><span class="sxs-lookup"><span data-stu-id="4fcfb-106">Member</span></span>|<span data-ttu-id="4fcfb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fcfb-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="4fcfb-108">Indica il contesto nel thread corrente nel momento in cui il Common Language Runtime (CLR) chiama il metodo [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) o il contesto richiesto da CLR in una chiamata a [IHostSecurityManager:: SetSecurityContext ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)metodo.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="4fcfb-109">Indica un contesto in cui l'host dispone di privilegi più bassi, ad esempio i costruttori di Garbage Collector o di classe o di modulo.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fcfb-110">Note</span><span class="sxs-lookup"><span data-stu-id="4fcfb-110">Remarks</span></span>  
 <span data-ttu-id="4fcfb-111">CLR fornisce uno dei valori `EContextType` come valore di parametro nelle chiamate ai metodi `IHostSecurityManager::GetSecurityContext` e `IHostSecurityManager::SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fcfb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fcfb-112">Requirements</span></span>  
 <span data-ttu-id="4fcfb-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fcfb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcfb-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4fcfb-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fcfb-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4fcfb-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fcfb-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcfb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcfb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fcfb-117">See also</span></span>

- [<span data-ttu-id="4fcfb-118">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4fcfb-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4fcfb-119">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="4fcfb-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="4fcfb-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="4fcfb-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
