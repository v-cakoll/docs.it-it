---
title: Enumerazione EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129424"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="df909-102">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="df909-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="df909-103">Consente all'host di fornire al Runtime informazioni sull'inizializzazione di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="df909-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df909-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df909-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="df909-105">Members</span><span class="sxs-lookup"><span data-stu-id="df909-105">Members</span></span>  
  
|<span data-ttu-id="df909-106">Member</span><span class="sxs-lookup"><span data-stu-id="df909-106">Member</span></span>|<span data-ttu-id="df909-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df909-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="df909-108">Nessun flag.</span><span class="sxs-lookup"><span data-stu-id="df909-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="df909-109">Informa il Common Language Runtime (CLR) che l'host non apporterà modifiche allo stato di sicurezza del dominio dell'applicazione nel metodo <xref:System.AppDomainManager.InitializeNewDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="df909-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df909-110">Note</span><span class="sxs-lookup"><span data-stu-id="df909-110">Remarks</span></span>  
 <span data-ttu-id="df909-111">Il metodo [ICLRDomainManager:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) accetta un parametro di tipo `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="df909-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df909-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df909-112">Requirements</span></span>  
 <span data-ttu-id="df909-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df909-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df909-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df909-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df909-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df909-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df909-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df909-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df909-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df909-117">See also</span></span>

- [<span data-ttu-id="df909-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="df909-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="df909-119">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="df909-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
