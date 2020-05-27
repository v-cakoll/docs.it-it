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
ms.openlocfilehash: 807e1ee831a43a4ef1e7b0a269ee38131f24081e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008118"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="f2429-102">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f2429-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="f2429-103">Fornisce metodi che supportano il modello autodescrittivo impiegato da Common Language Runtime per la risoluzione e l'uso delle risorse.</span><span class="sxs-lookup"><span data-stu-id="f2429-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2429-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f2429-104">Methods</span></span>  
  
|<span data-ttu-id="f2429-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2429-105">Method</span></span>|<span data-ttu-id="f2429-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2429-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2429-107">Metodo DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="f2429-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="f2429-108">Crea una struttura dati che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="f2429-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f2429-109">Metodo DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="f2429-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="f2429-110">Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="f2429-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f2429-111">Metodo DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="f2429-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="f2429-112">Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="f2429-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f2429-113">Metodo DefineFile</span><span class="sxs-lookup"><span data-stu-id="f2429-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="f2429-114">Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="f2429-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f2429-115">Metodo DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="f2429-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="f2429-116">Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="f2429-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f2429-117">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="f2429-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="f2429-118">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="f2429-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="f2429-119">Metodo SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="f2429-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="f2429-120">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="f2429-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="f2429-121">Metodo SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="f2429-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="f2429-122">Modifica la struttura dei metadati `ExportedType` specificata.</span><span class="sxs-lookup"><span data-stu-id="f2429-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="f2429-123">Metodo SetFileProps</span><span class="sxs-lookup"><span data-stu-id="f2429-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="f2429-124">Modifica la struttura dei metadati `File` specificata.</span><span class="sxs-lookup"><span data-stu-id="f2429-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="f2429-125">Metodo SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="f2429-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="f2429-126">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="f2429-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2429-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f2429-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2429-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2429-128">Requirements</span></span>  
 <span data-ttu-id="f2429-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2429-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2429-130">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f2429-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2429-131">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f2429-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2429-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2429-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2429-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2429-133">See also</span></span>

- [<span data-ttu-id="f2429-134">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="f2429-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f2429-135">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="f2429-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
