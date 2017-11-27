---
title: Enumerazione EInitializeNewDomainFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EInitializeNewDomainFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EInitializeNewDomainFlags
helpviewer_keywords: EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bee1c5086502a9675e8149e7d6c9bc72f573815c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="9bc13-102">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="9bc13-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="9bc13-103">Consente all'host di fornire il runtime con informazioni sull'inizializzazione di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9bc13-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bc13-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9bc13-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9bc13-105">Members</span></span>  
  
|<span data-ttu-id="9bc13-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9bc13-106">Member</span></span>|<span data-ttu-id="9bc13-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bc13-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="9bc13-108">Nessun flag.</span><span class="sxs-lookup"><span data-stu-id="9bc13-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="9bc13-109">Informa common language runtime (CLR) che l'host non verrà apportate modifiche allo stato di sicurezza del dominio applicazione di <xref:System.AppDomainManager.InitializeNewDomain%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="9bc13-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bc13-110">Note</span><span class="sxs-lookup"><span data-stu-id="9bc13-110">Remarks</span></span>  
 <span data-ttu-id="9bc13-111">Il [ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) metodo accetta un parametro di tipo `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="9bc13-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc13-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bc13-112">Requirements</span></span>  
 <span data-ttu-id="9bc13-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bc13-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc13-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9bc13-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9bc13-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9bc13-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bc13-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc13-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc13-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bc13-117">See Also</span></span>  
 [<span data-ttu-id="9bc13-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="9bc13-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="9bc13-119">SetAppDomainManagerType (metodo)</span><span class="sxs-lookup"><span data-stu-id="9bc13-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
