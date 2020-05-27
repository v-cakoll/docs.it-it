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
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009015"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="ed804-102">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ed804-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="ed804-103">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ed804-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed804-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ed804-104">Methods</span></span>  
  
|<span data-ttu-id="ed804-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ed804-105">Method</span></span>|<span data-ttu-id="ed804-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed804-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed804-107">Metodo CloseEnum</span><span class="sxs-lookup"><span data-stu-id="ed804-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="ed804-108">Rilascia l'handle all'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="ed804-109">Metodo EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="ed804-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="ed804-110">Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdAssemblyRef` token degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ed804-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="ed804-111">Metodo EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="ed804-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="ed804-112">Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdExportedType` token dei tipi com a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ed804-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="ed804-113">Metodo EnumFiles</span><span class="sxs-lookup"><span data-stu-id="ed804-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="ed804-114">Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdFile` token dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ed804-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="ed804-115">Metodo EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="ed804-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="ed804-116">Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ed804-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="ed804-117">Metodo FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="ed804-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="ed804-118">Ottiene una matrice di `mdAssemblyRef` token per gli assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="ed804-119">Metodo FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="ed804-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="ed804-120">Ottiene un `mdExportedType` token per il tipo com con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="ed804-121">Metodo FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="ed804-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="ed804-122">Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="ed804-123">Metodo GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="ed804-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="ed804-124">Ottiene il token per l'assembly nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="ed804-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="ed804-125">Metodo GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="ed804-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="ed804-126">Ottiene le impostazioni delle proprietà dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="ed804-127">Metodo GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="ed804-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="ed804-128">Ottiene le impostazioni della proprietà del `mdAssemblyRef` token specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="ed804-129">Metodo GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="ed804-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="ed804-130">Ottiene le impostazioni della proprietà del tipo COM specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="ed804-131">Metodo GetFileProps</span><span class="sxs-lookup"><span data-stu-id="ed804-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="ed804-132">Ottiene le impostazioni della proprietà del file specificato.</span><span class="sxs-lookup"><span data-stu-id="ed804-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="ed804-133">Metodo GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="ed804-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="ed804-134">Ottiene le impostazioni della proprietà della risorsa di manifesto specificata.</span><span class="sxs-lookup"><span data-stu-id="ed804-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed804-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed804-135">Requirements</span></span>  
 <span data-ttu-id="ed804-136">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed804-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed804-137">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed804-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed804-138">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed804-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed804-139">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed804-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed804-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed804-140">See also</span></span>

- [<span data-ttu-id="ed804-141">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="ed804-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="ed804-142">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="ed804-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
