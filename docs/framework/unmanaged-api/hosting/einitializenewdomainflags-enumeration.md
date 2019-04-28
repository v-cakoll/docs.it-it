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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628626"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="afed7-102">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="afed7-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="afed7-103">Consente all'host di fornire il runtime con informazioni sull'inizializzazione di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afed7-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afed7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afed7-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="afed7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="afed7-105">Members</span></span>  
  
|<span data-ttu-id="afed7-106">Member</span><span class="sxs-lookup"><span data-stu-id="afed7-106">Member</span></span>|<span data-ttu-id="afed7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afed7-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="afed7-108">Nessun flag.</span><span class="sxs-lookup"><span data-stu-id="afed7-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="afed7-109">Indica che l'host non apporterà le modifiche allo stato di sicurezza del dominio dell'applicazione in a common language runtime (CLR) di <xref:System.AppDomainManager.InitializeNewDomain%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="afed7-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afed7-110">Note</span><span class="sxs-lookup"><span data-stu-id="afed7-110">Remarks</span></span>  
 <span data-ttu-id="afed7-111">Il [ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) metodo accetta un parametro di tipo `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="afed7-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afed7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afed7-112">Requirements</span></span>  
 <span data-ttu-id="afed7-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afed7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afed7-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="afed7-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afed7-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afed7-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afed7-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afed7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afed7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afed7-117">See also</span></span>

- [<span data-ttu-id="afed7-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="afed7-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="afed7-119">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="afed7-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
