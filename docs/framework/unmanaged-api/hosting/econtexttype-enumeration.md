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
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493416"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="53e16-102">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="53e16-102">EContextType Enumeration</span></span>
<span data-ttu-id="53e16-103">Descrive il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="53e16-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53e16-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="53e16-105">Membri</span><span class="sxs-lookup"><span data-stu-id="53e16-105">Members</span></span>  
  
|<span data-ttu-id="53e16-106">Membro</span><span class="sxs-lookup"><span data-stu-id="53e16-106">Member</span></span>|<span data-ttu-id="53e16-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53e16-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="53e16-108">Indica il contesto nel thread corrente nel momento in cui il Common Language Runtime (CLR) chiama il metodo [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) o il contesto richiesto da CLR in una chiamata al metodo [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="53e16-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="53e16-109">Indica un contesto in cui l'host dispone di privilegi più bassi, ad esempio i costruttori di Garbage Collector o di classe o di modulo.</span><span class="sxs-lookup"><span data-stu-id="53e16-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53e16-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="53e16-110">Remarks</span></span>  
 <span data-ttu-id="53e16-111">CLR fornisce uno dei `EContextType` valori come valore di parametro nelle chiamate ai `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` metodi e.</span><span class="sxs-lookup"><span data-stu-id="53e16-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e16-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53e16-112">Requirements</span></span>  
 <span data-ttu-id="53e16-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e16-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e16-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53e16-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53e16-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53e16-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53e16-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e16-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e16-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53e16-117">See also</span></span>

- [<span data-ttu-id="53e16-118">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="53e16-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="53e16-119">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="53e16-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="53e16-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="53e16-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
