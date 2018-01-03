---
title: Interfaccia ICorDebugSymbolProvider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63823c535ad4d036dd5d539c8fe5381d350ccbe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="30834-102">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="30834-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="30834-103">Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="30834-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30834-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="30834-104">Methods</span></span>  
  
|<span data-ttu-id="30834-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="30834-105">Method</span></span>|<span data-ttu-id="30834-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30834-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30834-107">Metodo GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="30834-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="30834-108">Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="30834-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="30834-109">Metodo GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="30834-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="30834-110">Restituisce i metadati da un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="30834-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="30834-111">Metodo GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="30834-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="30834-112">Ottiene l'indirizzo iniziale del metodo e la dimensione sulla base di un indirizzo RVA (Relative Virtual Address) in un metodo.</span><span class="sxs-lookup"><span data-stu-id="30834-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="30834-113">Metodo GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="30834-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="30834-114">Ottiene i simboli dei campi di istanza che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="30834-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="30834-115">Metodo GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="30834-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="30834-116">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="30834-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="30834-117">Metodo GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="30834-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="30834-118">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="30834-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="30834-119">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="30834-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="30834-120">Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="30834-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="30834-121">Metodo GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="30834-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="30834-122">Restituisce informazioni sulle proprietà del metodo, ad esempio il token di metadati del metodo e informazioni sui relativi parametri generici, da un indirizzo RVA (Relative Virtual Address) fornito in tale metodo.</span><span class="sxs-lookup"><span data-stu-id="30834-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="30834-123">Metodo GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="30834-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="30834-124">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="30834-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="30834-125">Metodo GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="30834-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="30834-126">Ottiene i simboli dei campi statici che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="30834-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="30834-127">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="30834-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="30834-128">Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="30834-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30834-129">Note</span><span class="sxs-lookup"><span data-stu-id="30834-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30834-130">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="30834-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="30834-131">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="30834-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30834-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30834-132">Requirements</span></span>  
 <span data-ttu-id="30834-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30834-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30834-134">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="30834-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30834-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30834-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30834-136">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30834-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30834-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30834-137">See Also</span></span>  
 [<span data-ttu-id="30834-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30834-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="30834-139">Debug</span><span class="sxs-lookup"><span data-stu-id="30834-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
