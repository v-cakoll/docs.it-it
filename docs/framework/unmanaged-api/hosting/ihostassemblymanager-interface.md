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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c8d17723481fc5b41fe5f3006fe8db2c53d1ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438480"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="d398a-102">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d398a-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="d398a-103">Fornisce metodi che consentono a un host specificare i set di assembly che devono essere caricati da common language runtime (CLR) o dall'host.</span><span class="sxs-lookup"><span data-stu-id="d398a-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d398a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d398a-104">Methods</span></span>  
  
|<span data-ttu-id="d398a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d398a-105">Method</span></span>|<span data-ttu-id="d398a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d398a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d398a-107">Metodo GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d398a-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="d398a-108">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) che rappresenta l'elenco degli assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="d398a-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="d398a-109">Metodo GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="d398a-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="d398a-110">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che dovranno essere caricati da Common Language Runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="d398a-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d398a-111">Note</span><span class="sxs-lookup"><span data-stu-id="d398a-111">Remarks</span></span>  
 <span data-ttu-id="d398a-112">L'host non è necessario implementare `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="d398a-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="d398a-113">Se l'host implementa `IHostAssemblyManager`, deve anche implementare `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="d398a-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="d398a-114">Il runtime esegue una query per un `IHostAssemblyManager` chiamando [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) dopo l'inizializzazione con un `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="d398a-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d398a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d398a-115">Requirements</span></span>  
 <span data-ttu-id="d398a-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d398a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d398a-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d398a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d398a-118">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d398a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d398a-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d398a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d398a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d398a-120">See Also</span></span>  
 [<span data-ttu-id="d398a-121">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d398a-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="d398a-122">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d398a-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="d398a-123">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="d398a-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="d398a-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d398a-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
