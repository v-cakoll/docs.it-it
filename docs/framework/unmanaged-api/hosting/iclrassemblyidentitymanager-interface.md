---
title: Interfaccia ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b209e568b1e65ed785155d045cd48d1248672da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209801"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="d8fe3-102">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="d8fe3-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="d8fe3-103">Fornisce metodi che supportano la comunicazione tra l'host e common language runtime (CLR) sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8fe3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d8fe3-104">Methods</span></span>  
  
|<span data-ttu-id="d8fe3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d8fe3-105">Method</span></span>|<span data-ttu-id="d8fe3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8fe3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8fe3-107">Metodo GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="d8fe3-107">GetBindingIdentityFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="d8fe3-108">Ottiene l'identità dell'assembly data binding per l'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="d8fe3-109">Metodo GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="d8fe3-109">GetBindingIdentityFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="d8fe3-110">Ottiene i dati di identità di assembly canonico per l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="d8fe3-111">Metodo GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d8fe3-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="d8fe3-112">Ottiene un' [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) istanza dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-112">Gets an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="d8fe3-113">Metodo GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="d8fe3-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="d8fe3-114">Ottiene un' [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumeratore per le identità di assembly a cui fanno riferimento all'assembly con l'identità specificata.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-114">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="d8fe3-115">Metodo GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="d8fe3-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="d8fe3-116">Ottiene un' [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) istanza che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso file specificato.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-116">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="d8fe3-117">Metodo GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="d8fe3-117">GetReferencedAssembliesFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="d8fe3-118">Ottiene un puntatore a un `ICLRReferenceAssemblyEnum` oggetto contenente i dati di identità di assembly per gli assembly a cui fatto riferimento l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="d8fe3-119">Metodo IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="d8fe3-119">IsStronglyNamed Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="d8fe3-120">Ottiene un valore che indica se l'assembly specificato è un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8fe3-121">Note</span><span class="sxs-lookup"><span data-stu-id="d8fe3-121">Remarks</span></span>  
 <span data-ttu-id="d8fe3-122">Uso `ICLRAssemblyIdentityManager` per ottenere le istanze di `ICLRAssemblyReferenceList` ed enumerare le identità di assembly.</span><span class="sxs-lookup"><span data-stu-id="d8fe3-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8fe3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8fe3-123">Requirements</span></span>  
 <span data-ttu-id="d8fe3-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8fe3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8fe3-125">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8fe3-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8fe3-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d8fe3-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8fe3-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8fe3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fe3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8fe3-128">See also</span></span>

- [<span data-ttu-id="d8fe3-129">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d8fe3-129">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d8fe3-130">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="d8fe3-130">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="d8fe3-131">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d8fe3-131">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
