---
title: Interfaccia ICLRDomainManager
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103923"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="9a137-102">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="9a137-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="9a137-103">Consente all'host specificare il gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito e specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="9a137-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a137-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9a137-104">Methods</span></span>  
  
|<span data-ttu-id="9a137-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9a137-105">Method</span></span>|<span data-ttu-id="9a137-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a137-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a137-107">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="9a137-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="9a137-108">Specifica il tipo, derivato dal <xref:System.AppDomainManager?displayProperty=nameWithType> (classe), l'applicazione del gestore del dominio che verrà usato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="9a137-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="9a137-109">Metodo SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="9a137-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="9a137-110">Imposta le proprietà che verranno usate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="9a137-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a137-111">Note</span><span class="sxs-lookup"><span data-stu-id="9a137-111">Remarks</span></span>  
 <span data-ttu-id="9a137-112">Per ottenere un'istanza di questa interfaccia, chiamare il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo con il tipo di gestione IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="9a137-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a137-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a137-113">Requirements</span></span>  
 <span data-ttu-id="9a137-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a137-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a137-115">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9a137-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a137-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9a137-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9a137-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9a137-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a137-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a137-118">See also</span></span>

- [<span data-ttu-id="9a137-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9a137-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9a137-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="9a137-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
