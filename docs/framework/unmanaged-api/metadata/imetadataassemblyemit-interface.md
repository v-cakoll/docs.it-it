---
title: Interfaccia IMetaDataAssemblyEmit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af7a5fd5a564aa7366924f47b0c526aff7153521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="a6bb6-102">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a6bb6-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="a6bb6-103">Fornisce metodi che supportano il modello autodescrittivo impiegato da Common Language Runtime per la risoluzione e l'uso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6bb6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a6bb6-104">Methods</span></span>  
  
|<span data-ttu-id="a6bb6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a6bb6-105">Method</span></span>|<span data-ttu-id="a6bb6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6bb6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6bb6-107">DefineAssembly (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="a6bb6-108">Crea una struttura dati che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a6bb6-109">DefineAssemblyRef (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="a6bb6-110">Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a6bb6-111">DefineExportedType (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="a6bb6-112">Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a6bb6-113">DefineFile (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="a6bb6-114">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a6bb6-115">DefineManifestResource (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="a6bb6-116">Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="a6bb6-117">SetAssemblyProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="a6bb6-118">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="a6bb6-119">SetAssemblyRefProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="a6bb6-120">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="a6bb6-121">SetExportedTypeProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="a6bb6-122">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="a6bb6-123">SetFileProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="a6bb6-124">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="a6bb6-125">SetManifestResourceProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="a6bb6-126">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="a6bb6-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6bb6-127">Note</span><span class="sxs-lookup"><span data-stu-id="a6bb6-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6bb6-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6bb6-128">Requirements</span></span>  
 <span data-ttu-id="a6bb6-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6bb6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6bb6-130">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6bb6-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6bb6-131">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6bb6-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6bb6-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6bb6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bb6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6bb6-133">See Also</span></span>  
 [<span data-ttu-id="a6bb6-134">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="a6bb6-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="a6bb6-135">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6bb6-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
