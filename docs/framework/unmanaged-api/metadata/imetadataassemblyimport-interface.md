---
title: Interfaccia IMetaDataAssemblyImport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef5b913dc9b1391c63cb123e1f922ca61da6a5bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="41457-102">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="41457-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="41457-103">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="41457-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41457-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="41457-104">Methods</span></span>  
  
|<span data-ttu-id="41457-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="41457-105">Method</span></span>|<span data-ttu-id="41457-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41457-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41457-107">CloseEnum (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="41457-108">Rilascia l'handle per l'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="41457-109">EnumAssemblyRefs (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="41457-110">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdAssemblyRef` token degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="41457-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41457-111">EnumExportedTypes (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="41457-112">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdExportedType` token dei tipi COM a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="41457-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41457-113">EnumFiles (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="41457-114">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdFile` token dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="41457-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41457-115">EnumManifestResources (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="41457-116">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="41457-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41457-117">FindAssembliesByName (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="41457-118">Ottiene una matrice di `mdAssemblyRef` token per gli assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="41457-119">FindExportedTypeByName (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="41457-120">Ottiene un `mdExportedType` token per il tipo COM con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="41457-121">FindManifestResourceByName (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="41457-122">Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="41457-123">GetAssemblyFromScope (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="41457-124">Ottiene il token per l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="41457-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="41457-125">GetAssemblyProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="41457-126">Ottiene le impostazioni delle proprietà dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="41457-127">GetAssemblyRefProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="41457-128">Ottiene le impostazioni delle proprietà dell'oggetto specificato `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="41457-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="41457-129">GetExportedTypeProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="41457-130">Ottiene le impostazioni delle proprietà del tipo COM specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="41457-131">GetFileProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="41457-132">Ottiene le impostazioni delle proprietà del file specificato.</span><span class="sxs-lookup"><span data-stu-id="41457-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="41457-133">GetManifestResourceProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="41457-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="41457-134">Ottiene le impostazioni delle proprietà della risorsa del manifesto specificata.</span><span class="sxs-lookup"><span data-stu-id="41457-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41457-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41457-135">Requirements</span></span>  
 <span data-ttu-id="41457-136">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41457-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41457-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41457-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41457-138">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41457-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41457-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41457-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41457-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41457-140">See Also</span></span>  
 [<span data-ttu-id="41457-141">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="41457-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="41457-142">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="41457-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
