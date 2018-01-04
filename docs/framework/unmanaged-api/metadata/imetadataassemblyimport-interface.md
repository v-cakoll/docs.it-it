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
ms.workload: dotnet
ms.openlocfilehash: 992b588d16bc221f6b72044da40d09fbb6894511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="cac66-102">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="cac66-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="cac66-103">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="cac66-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cac66-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cac66-104">Methods</span></span>  
  
|<span data-ttu-id="cac66-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cac66-105">Method</span></span>|<span data-ttu-id="cac66-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cac66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cac66-107">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="cac66-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="cac66-108">Rilascia l'handle per l'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="cac66-109">Metodo EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="cac66-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="cac66-110">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdAssemblyRef` token degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cac66-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="cac66-111">Metodo EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="cac66-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="cac66-112">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdExportedType` token dei tipi COM a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cac66-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="cac66-113">Metodo EnumFiles</span><span class="sxs-lookup"><span data-stu-id="cac66-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="cac66-114">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdFile` token dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cac66-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="cac66-115">Metodo EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="cac66-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="cac66-116">Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cac66-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="cac66-117">Metodo FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="cac66-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="cac66-118">Ottiene una matrice di `mdAssemblyRef` token per gli assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="cac66-119">Metodo FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="cac66-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="cac66-120">Ottiene un `mdExportedType` token per il tipo COM con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="cac66-121">Metodo FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="cac66-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="cac66-122">Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="cac66-123">Metodo GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="cac66-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="cac66-124">Ottiene il token per l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cac66-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="cac66-125">Metodo GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="cac66-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="cac66-126">Ottiene le impostazioni delle proprietà dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="cac66-127">Metodo GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="cac66-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="cac66-128">Ottiene le impostazioni delle proprietà dell'oggetto specificato `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="cac66-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="cac66-129">Metodo GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="cac66-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="cac66-130">Ottiene le impostazioni delle proprietà del tipo COM specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="cac66-131">Metodo GetFileProps</span><span class="sxs-lookup"><span data-stu-id="cac66-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="cac66-132">Ottiene le impostazioni delle proprietà del file specificato.</span><span class="sxs-lookup"><span data-stu-id="cac66-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="cac66-133">Metodo GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="cac66-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="cac66-134">Ottiene le impostazioni delle proprietà della risorsa del manifesto specificata.</span><span class="sxs-lookup"><span data-stu-id="cac66-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cac66-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cac66-135">Requirements</span></span>  
 <span data-ttu-id="cac66-136">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cac66-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac66-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cac66-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cac66-138">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cac66-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cac66-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cac66-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac66-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cac66-140">See Also</span></span>  
 [<span data-ttu-id="cac66-141">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="cac66-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="cac66-142">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="cac66-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
