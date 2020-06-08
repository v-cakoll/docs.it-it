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
ms.openlocfilehash: 4e32a36a4cf751bf7c5a2c918fde0122f21b7878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501592"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="d7f88-102">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d7f88-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="d7f88-103">Fornisce metodi che consentono a un host di specificare set di assembly che devono essere caricati dal Common Language Runtime (CLR) o dall'host.</span><span class="sxs-lookup"><span data-stu-id="d7f88-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7f88-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7f88-104">Methods</span></span>  
  
|<span data-ttu-id="d7f88-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7f88-105">Method</span></span>|<span data-ttu-id="d7f88-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7f88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7f88-107">Metodo GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d7f88-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="d7f88-108">Ottiene un puntatore a interfaccia a un [IHostAssemblyStore](ihostassemblystore-interface.md) che rappresenta l'elenco di assembly caricati dall'host.</span><span class="sxs-lookup"><span data-stu-id="d7f88-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="d7f88-109">Metodo GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="d7f88-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="d7f88-110">Ottiene un puntatore a interfaccia a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) che rappresenta l'elenco di assembly che l'host prevede venga caricato da CLR.</span><span class="sxs-lookup"><span data-stu-id="d7f88-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7f88-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d7f88-111">Remarks</span></span>  
 <span data-ttu-id="d7f88-112">L'host non deve implementare `IHostAssemblyManager` o `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="d7f88-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="d7f88-113">Se l'host implementa `IHostAssemblyManager` , deve implementare anche `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="d7f88-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="d7f88-114">Il runtime esegue una query per un oggetto `IHostAssemblyManager` chiamando [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) al momento dell'inizializzazione con un oggetto `IID` di IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="d7f88-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f88-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7f88-115">Requirements</span></span>  
 <span data-ttu-id="d7f88-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f88-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f88-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d7f88-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7f88-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7f88-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7f88-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f88-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f88-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7f88-120">See also</span></span>

- [<span data-ttu-id="d7f88-121">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d7f88-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d7f88-122">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="d7f88-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="d7f88-123">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="d7f88-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="d7f88-124">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d7f88-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
