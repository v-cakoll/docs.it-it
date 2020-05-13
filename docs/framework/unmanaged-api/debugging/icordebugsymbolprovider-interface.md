---
title: Interfaccia ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 25faad4f4bc67b57c339bc63d1a18ab4d275cd71
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379346"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="e018a-102">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="e018a-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="e018a-103">Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug.</span><span class="sxs-lookup"><span data-stu-id="e018a-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e018a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e018a-104">Methods</span></span>  
  
|<span data-ttu-id="e018a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e018a-105">Method</span></span>|<span data-ttu-id="e018a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e018a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e018a-107">Metodo GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="e018a-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="e018a-108">Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="e018a-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="e018a-109">Metodo GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="e018a-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="e018a-110">Restituisce i metadati da un assembly sottoposto a merge.</span><span class="sxs-lookup"><span data-stu-id="e018a-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="e018a-111">Metodo GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="e018a-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="e018a-112">Ottiene l'indirizzo iniziale del metodo e la dimensione sulla base di un indirizzo RVA (Relative Virtual Address) in un metodo.</span><span class="sxs-lookup"><span data-stu-id="e018a-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="e018a-113">Metodo GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="e018a-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="e018a-114">Ottiene i simboli dei campi di istanza che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e018a-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e018a-115">Metodo GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="e018a-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="e018a-116">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="e018a-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="e018a-117">Metodo GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="e018a-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="e018a-118">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="e018a-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e018a-119">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="e018a-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="e018a-120">Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="e018a-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e018a-121">Metodo GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="e018a-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="e018a-122">Restituisce informazioni sulle proprietà del metodo, ad esempio il token di metadati del metodo e informazioni sui relativi parametri generici, da un indirizzo RVA (Relative Virtual Address) fornito in tale metodo.</span><span class="sxs-lookup"><span data-stu-id="e018a-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="e018a-123">Metodo GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="e018a-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="e018a-124">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e018a-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="e018a-125">Metodo GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="e018a-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="e018a-126">Ottiene i simboli dei campi statici che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e018a-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e018a-127">Metodo GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="e018a-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="e018a-128">Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.</span><span class="sxs-lookup"><span data-stu-id="e018a-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e018a-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e018a-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e018a-130">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e018a-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e018a-131">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e018a-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e018a-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e018a-132">Requirements</span></span>  
 <span data-ttu-id="e018a-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e018a-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e018a-134">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e018a-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e018a-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e018a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e018a-136">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e018a-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e018a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e018a-137">See also</span></span>

- [<span data-ttu-id="e018a-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e018a-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e018a-139">Debug</span><span class="sxs-lookup"><span data-stu-id="e018a-139">Debugging</span></span>](index.md)
