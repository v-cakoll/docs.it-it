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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129335"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="4bc1e-102">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="4bc1e-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="4bc1e-103">Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="4bc1e-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bc1e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4bc1e-104">Methods</span></span>  
  
|<span data-ttu-id="4bc1e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4bc1e-105">Method</span></span>|<span data-ttu-id="4bc1e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bc1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bc1e-107">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="4bc1e-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="4bc1e-108">Specifica il tipo, derivato dalla classe <xref:System.AppDomainManager?displayProperty=nameWithType>, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="4bc1e-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="4bc1e-109">Metodo SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="4bc1e-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="4bc1e-110">Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="4bc1e-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bc1e-111">Note</span><span class="sxs-lookup"><span data-stu-id="4bc1e-111">Remarks</span></span>  
 <span data-ttu-id="4bc1e-112">Per ottenere un'istanza di questa interfaccia, chiamare il metodo [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) con l'IID del tipo di gestione `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="4bc1e-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc1e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bc1e-113">Requirements</span></span>  
 <span data-ttu-id="4bc1e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bc1e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc1e-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4bc1e-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4bc1e-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4bc1e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bc1e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc1e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc1e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bc1e-118">See also</span></span>

- [<span data-ttu-id="4bc1e-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4bc1e-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4bc1e-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="4bc1e-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
