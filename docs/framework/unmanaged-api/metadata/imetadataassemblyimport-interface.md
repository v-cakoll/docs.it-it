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
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436302"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="95e1a-102">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="95e1a-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="95e1a-103">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="95e1a-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95e1a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="95e1a-104">Methods</span></span>  
  
|<span data-ttu-id="95e1a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="95e1a-105">Method</span></span>|<span data-ttu-id="95e1a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95e1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95e1a-107">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="95e1a-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="95e1a-108">Rilascia l'handle all'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="95e1a-109">Metodo EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="95e1a-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="95e1a-110">Ottiene un puntatore a interfaccia a un enumeratore che contiene i token `mdAssemblyRef` degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="95e1a-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="95e1a-111">Metodo EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="95e1a-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="95e1a-112">Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdExportedType` dei tipi COM a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="95e1a-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="95e1a-113">Metodo EnumFiles</span><span class="sxs-lookup"><span data-stu-id="95e1a-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="95e1a-114">Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdFile` dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="95e1a-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="95e1a-115">Metodo EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="95e1a-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="95e1a-116">Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdManifestResource` delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="95e1a-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="95e1a-117">Metodo FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="95e1a-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="95e1a-118">Ottiene una matrice di token `mdAssemblyRef` per gli assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="95e1a-119">Metodo FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="95e1a-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="95e1a-120">Ottiene un token di `mdExportedType` per il tipo COM con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="95e1a-121">Metodo FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="95e1a-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="95e1a-122">Ottiene un token di `mdManifestResource` per la risorsa con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="95e1a-123">Metodo GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="95e1a-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="95e1a-124">Ottiene il token per l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="95e1a-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="95e1a-125">Metodo GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="95e1a-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="95e1a-126">Ottiene le impostazioni delle proprietà dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="95e1a-127">Metodo GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="95e1a-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="95e1a-128">Ottiene le impostazioni della proprietà del token di `mdAssemblyRef` specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="95e1a-129">Metodo GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="95e1a-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="95e1a-130">Ottiene le impostazioni della proprietà del tipo COM specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="95e1a-131">Metodo GetFileProps</span><span class="sxs-lookup"><span data-stu-id="95e1a-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="95e1a-132">Ottiene le impostazioni della proprietà del file specificato.</span><span class="sxs-lookup"><span data-stu-id="95e1a-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="95e1a-133">Metodo GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="95e1a-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="95e1a-134">Ottiene le impostazioni della proprietà della risorsa di manifesto specificata.</span><span class="sxs-lookup"><span data-stu-id="95e1a-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e1a-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95e1a-135">Requirements</span></span>  
 <span data-ttu-id="95e1a-136">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e1a-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e1a-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95e1a-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95e1a-138">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="95e1a-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95e1a-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e1a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e1a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95e1a-140">See also</span></span>

- [<span data-ttu-id="95e1a-141">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="95e1a-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="95e1a-142">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="95e1a-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
