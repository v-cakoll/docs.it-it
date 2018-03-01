---
title: Interfaccia IHostAssemblyManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 351824c1b915183a8e157f5bb2e01a414027a178
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="c106f-102">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c106f-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="c106f-103">Fornisce metodi che consentono a un host specificare i set di assembly che devono essere caricati da common language runtime (CLR) o dall'host.</span><span class="sxs-lookup"><span data-stu-id="c106f-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c106f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c106f-104">Methods</span></span>  
  
|<span data-ttu-id="c106f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c106f-105">Method</span></span>|<span data-ttu-id="c106f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c106f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c106f-107">Metodo GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c106f-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="c106f-108">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco degli assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="c106f-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="c106f-109">Metodo GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="c106f-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="c106f-110">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che dovranno essere caricati da Common Language Runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="c106f-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c106f-111">Note</span><span class="sxs-lookup"><span data-stu-id="c106f-111">Remarks</span></span>  
 <span data-ttu-id="c106f-112">L'host non è necessario implementare `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c106f-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="c106f-113">Se l'host implementa `IHostAssemblyManager`, deve anche implementare `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="c106f-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="c106f-114">Il runtime esegue una query per un `IHostAssemblyManager` chiamando [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) dopo l'inizializzazione con un `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="c106f-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c106f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c106f-115">Requirements</span></span>  
 <span data-ttu-id="c106f-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c106f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c106f-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c106f-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c106f-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c106f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c106f-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c106f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c106f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c106f-120">See Also</span></span>  
 [<span data-ttu-id="c106f-121">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c106f-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="c106f-122">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c106f-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="c106f-123">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="c106f-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="c106f-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c106f-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
