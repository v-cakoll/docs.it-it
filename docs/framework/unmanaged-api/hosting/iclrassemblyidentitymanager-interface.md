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
ms.openlocfilehash: 3611de471001d31c40984e71d49ce376bb3e4607
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504290"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="a40a3-102">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a40a3-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="a40a3-103">Fornisce metodi che supportano la comunicazione tra l'host e il Common Language Runtime (CLR) sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="a40a3-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a40a3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a40a3-104">Methods</span></span>  
  
|<span data-ttu-id="a40a3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a40a3-105">Method</span></span>|<span data-ttu-id="a40a3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a40a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a40a3-107">Metodo GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="a40a3-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="a40a3-108">Ottiene i dati dell'associazione di identità dell'assembly per l'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="a40a3-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="a40a3-109">Metodo GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="a40a3-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="a40a3-110">Ottiene i dati di identità dell'assembly canonico per l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="a40a3-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="a40a3-111">Metodo GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a40a3-111">GetCLRAssemblyReferenceList Method</span></span>](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="a40a3-112">Ottiene un'istanza di [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) dall'elenco fornito di identità di assembly parziali.</span><span class="sxs-lookup"><span data-stu-id="a40a3-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="a40a3-113">Metodo GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="a40a3-113">GetProbingAssembliesFromReference Method</span></span>](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="a40a3-114">Ottiene un enumeratore [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) per le identità di assembly a cui fa riferimento l'assembly con l'identità specificata.</span><span class="sxs-lookup"><span data-stu-id="a40a3-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="a40a3-115">Metodo GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="a40a3-115">GetReferencedAssembliesFromFile Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="a40a3-116">Ottiene un'istanza di [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) che contiene un elenco di assembly a cui fa riferimento l'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="a40a3-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="a40a3-117">Metodo GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="a40a3-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="a40a3-118">Ottiene un puntatore a un `ICLRReferenceAssemblyEnum` oggetto che contiene i dati di identità dell'assembly per gli assembly a cui fa riferimento l'assembly nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="a40a3-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="a40a3-119">Metodo IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="a40a3-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="a40a3-120">Ottiene un valore che indica se l'assembly specificato ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a40a3-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a40a3-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a40a3-121">Remarks</span></span>  
 <span data-ttu-id="a40a3-122">Utilizzare `ICLRAssemblyIdentityManager` per ottenere le istanze di `ICLRAssemblyReferenceList` e per enumerare le identità degli assembly.</span><span class="sxs-lookup"><span data-stu-id="a40a3-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a40a3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a40a3-123">Requirements</span></span>  
 <span data-ttu-id="a40a3-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a40a3-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40a3-125">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a40a3-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a40a3-126">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a40a3-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a40a3-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40a3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40a3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a40a3-128">See also</span></span>

- [<span data-ttu-id="a40a3-129">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a40a3-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a40a3-130">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a40a3-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="a40a3-131">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a40a3-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
