---
title: Interfaccia ICLRDomainManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5681d4776205569ea23aef2acb6d07c059419018
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="6e72e-102">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="6e72e-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="6e72e-103">Consente all'host specificare la gestione del dominio applicazione che verrà utilizzata per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="6e72e-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e72e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6e72e-104">Methods</span></span>  
  
|<span data-ttu-id="6e72e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6e72e-105">Method</span></span>|<span data-ttu-id="6e72e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e72e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e72e-107">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="6e72e-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="6e72e-108">Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore di dominio che verrà utilizzato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="6e72e-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="6e72e-109">Metodo SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="6e72e-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="6e72e-110">Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="6e72e-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e72e-111">Note</span><span class="sxs-lookup"><span data-stu-id="6e72e-111">Remarks</span></span>  
 <span data-ttu-id="6e72e-112">Per ottenere un'istanza di questa interfaccia, chiamare il [ICLRControl::](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo con il tipo di gestore IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="6e72e-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e72e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e72e-113">Requirements</span></span>  
 <span data-ttu-id="6e72e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e72e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e72e-115">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="6e72e-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6e72e-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e72e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e72e-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e72e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e72e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e72e-118">See Also</span></span>  
 [<span data-ttu-id="6e72e-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6e72e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6e72e-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="6e72e-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
