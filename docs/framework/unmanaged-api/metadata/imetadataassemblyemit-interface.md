---
title: Interfaccia IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 6b36d63101c1e9550a979d858764e9052cf45792
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447927"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="38bad-102">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="38bad-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="38bad-103">Fornisce metodi che supportano il modello autodescrittivo impiegato da Common Language Runtime per la risoluzione e l'uso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="38bad-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38bad-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="38bad-104">Methods</span></span>  
  
|<span data-ttu-id="38bad-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="38bad-105">Method</span></span>|<span data-ttu-id="38bad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38bad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38bad-107">Metodo DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="38bad-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="38bad-108">Crea una struttura dati che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="38bad-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="38bad-109">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="38bad-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="38bad-110">Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="38bad-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="38bad-111">Metodo DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="38bad-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="38bad-112">Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="38bad-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="38bad-113">Metodo DefineFile</span><span class="sxs-lookup"><span data-stu-id="38bad-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="38bad-114">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="38bad-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="38bad-115">Metodo DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="38bad-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="38bad-116">Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="38bad-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="38bad-117">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="38bad-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="38bad-118">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="38bad-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="38bad-119">Metodo SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="38bad-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="38bad-120">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="38bad-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="38bad-121">Metodo SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="38bad-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="38bad-122">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="38bad-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="38bad-123">Metodo SetFileProps</span><span class="sxs-lookup"><span data-stu-id="38bad-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="38bad-124">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="38bad-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="38bad-125">Metodo SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="38bad-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="38bad-126">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="38bad-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38bad-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="38bad-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38bad-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38bad-128">Requirements</span></span>  
 <span data-ttu-id="38bad-129">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38bad-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38bad-130">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="38bad-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38bad-131">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="38bad-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38bad-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38bad-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38bad-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38bad-133">See also</span></span>

- [<span data-ttu-id="38bad-134">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="38bad-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="38bad-135">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="38bad-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
