---
title: Interfaccia IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124513"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="be79e-102">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="be79e-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="be79e-103">Fornisce metodi che consentono a un host di specificare set di assembly che devono essere caricati dal Common Language Runtime (CLR) o dall'host.</span><span class="sxs-lookup"><span data-stu-id="be79e-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be79e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="be79e-104">Methods</span></span>  
  
|<span data-ttu-id="be79e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="be79e-105">Method</span></span>|<span data-ttu-id="be79e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be79e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be79e-107">Metodo GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="be79e-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="be79e-108">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="be79e-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="be79e-109">Metodo GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="be79e-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="be79e-110">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato da CLR.</span><span class="sxs-lookup"><span data-stu-id="be79e-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be79e-111">Note</span><span class="sxs-lookup"><span data-stu-id="be79e-111">Remarks</span></span>  
 <span data-ttu-id="be79e-112">Non è necessario che l'host implementi `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="be79e-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="be79e-113">Se l'host implementa `IHostAssemblyManager`, deve implementare anche `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="be79e-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="be79e-114">Il runtime esegue una query per un `IHostAssemblyManager` chiamando [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) al momento dell'inizializzazione con una `IID` di IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="be79e-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be79e-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be79e-115">Requirements</span></span>  
 <span data-ttu-id="be79e-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be79e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be79e-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="be79e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be79e-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="be79e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be79e-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be79e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be79e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be79e-120">See also</span></span>

- [<span data-ttu-id="be79e-121">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="be79e-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="be79e-122">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="be79e-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="be79e-123">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="be79e-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="be79e-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="be79e-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
