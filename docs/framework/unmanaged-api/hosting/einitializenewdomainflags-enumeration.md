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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616229"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="9e210-102">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="9e210-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="9e210-103">Consente all'host di fornire al Runtime informazioni sull'inizializzazione di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e210-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e210-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e210-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9e210-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9e210-105">Members</span></span>  
  
|<span data-ttu-id="9e210-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9e210-106">Member</span></span>|<span data-ttu-id="9e210-107">Description</span><span class="sxs-lookup"><span data-stu-id="9e210-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="9e210-108">Nessun flag.</span><span class="sxs-lookup"><span data-stu-id="9e210-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="9e210-109">Informa il Common Language Runtime (CLR) che l'host non apporterà modifiche allo stato di sicurezza del dominio dell'applicazione nel <xref:System.AppDomainManager.InitializeNewDomain%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9e210-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e210-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9e210-110">Remarks</span></span>  
 <span data-ttu-id="9e210-111">Il metodo [ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) accetta un parametro di tipo `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="9e210-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e210-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e210-112">Requirements</span></span>  
 <span data-ttu-id="9e210-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e210-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e210-114">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9e210-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e210-115">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9e210-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e210-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e210-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e210-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e210-117">See also</span></span>

- [<span data-ttu-id="9e210-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="9e210-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="9e210-119">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="9e210-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
