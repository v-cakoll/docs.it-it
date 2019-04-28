---
title: Interfaccia IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905411"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="938b5-102">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="938b5-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="938b5-103">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="938b5-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="938b5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="938b5-104">Methods</span></span>  
  
|<span data-ttu-id="938b5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="938b5-105">Method</span></span>|<span data-ttu-id="938b5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="938b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="938b5-107">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="938b5-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="938b5-108">Rilascia l'handle per l'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="938b5-109">Metodo EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="938b5-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="938b5-110">Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdAssemblyRef` token degli assembly a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="938b5-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="938b5-111">Metodo EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="938b5-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="938b5-112">Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdExportedType` i token dei tipi COM a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="938b5-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="938b5-113">Metodo EnumFiles</span><span class="sxs-lookup"><span data-stu-id="938b5-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="938b5-114">Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdFile` token dei file a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="938b5-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="938b5-115">Metodo EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="938b5-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="938b5-116">Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="938b5-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="938b5-117">Metodo FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="938b5-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="938b5-118">Ottiene una matrice di `mdAssemblyRef` i token per gli assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="938b5-119">Metodo FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="938b5-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="938b5-120">Ottiene un `mdExportedType` token per il tipo COM con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="938b5-121">Metodo FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="938b5-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="938b5-122">Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="938b5-123">Metodo GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="938b5-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="938b5-124">Ottiene il token per l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="938b5-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="938b5-125">Metodo GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="938b5-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="938b5-126">Ottiene le impostazioni delle proprietà dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="938b5-127">Metodo GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="938b5-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="938b5-128">Ottiene le impostazioni delle proprietà dell'oggetto specificato `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="938b5-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="938b5-129">Metodo GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="938b5-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="938b5-130">Ottiene le impostazioni delle proprietà del tipo COM specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="938b5-131">Metodo GetFileProps</span><span class="sxs-lookup"><span data-stu-id="938b5-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="938b5-132">Ottiene le impostazioni delle proprietà del file specificato.</span><span class="sxs-lookup"><span data-stu-id="938b5-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="938b5-133">Metodo GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="938b5-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="938b5-134">Ottiene le impostazioni delle proprietà della risorsa del manifesto specificata.</span><span class="sxs-lookup"><span data-stu-id="938b5-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="938b5-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="938b5-135">Requirements</span></span>  
 <span data-ttu-id="938b5-136">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="938b5-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="938b5-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="938b5-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="938b5-138">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="938b5-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="938b5-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="938b5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938b5-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="938b5-140">See also</span></span>

- [<span data-ttu-id="938b5-141">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="938b5-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="938b5-142">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="938b5-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
