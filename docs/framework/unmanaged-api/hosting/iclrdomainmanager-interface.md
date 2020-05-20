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
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615709"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="ea8bd-102">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="ea8bd-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="ea8bd-103">Consente all'host di specificare il gestore di dominio dell'applicazione che verrà utilizzato per inizializzare il dominio applicazione predefinito e per specificare le proprietà di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ea8bd-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea8bd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ea8bd-104">Methods</span></span>  
  
|<span data-ttu-id="ea8bd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ea8bd-105">Method</span></span>|<span data-ttu-id="ea8bd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea8bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea8bd-107">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="ea8bd-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="ea8bd-108">Specifica il tipo, derivato dalla <xref:System.AppDomainManager?displayProperty=nameWithType> classe, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="ea8bd-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="ea8bd-109">Metodo SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="ea8bd-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="ea8bd-110">Imposta le proprietà che verranno utilizzate per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="ea8bd-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea8bd-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea8bd-111">Remarks</span></span>  
 <span data-ttu-id="ea8bd-112">Per ottenere un'istanza di questa interfaccia, chiamare il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) con l'IID di tipo Manager `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="ea8bd-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8bd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea8bd-113">Requirements</span></span>  
 <span data-ttu-id="ea8bd-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8bd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8bd-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ea8bd-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ea8bd-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ea8bd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea8bd-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8bd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea8bd-118">See also</span></span>

- [<span data-ttu-id="ea8bd-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ea8bd-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ea8bd-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="ea8bd-120">Hosting</span></span>](index.md)
