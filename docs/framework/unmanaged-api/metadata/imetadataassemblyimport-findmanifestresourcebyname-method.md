---
title: Metodo IMetaDataAssemblyImport::FindManifestResourceByName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindManifestResourceByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 492f8a50c421df56d1b2f79d15d86ef3251b401e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="155e4-102">Metodo IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="155e4-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="155e4-103">Ottiene un puntatore alla risorsa di manifesto con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="155e4-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155e4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155e4-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="155e4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="155e4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="155e4-106">[in] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="155e4-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="155e4-107">[out] Matrice utilizzata per archiviare il `mdManifestResource` i token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.</span><span class="sxs-lookup"><span data-stu-id="155e4-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155e4-108">Note</span><span class="sxs-lookup"><span data-stu-id="155e4-108">Remarks</span></span>  
 <span data-ttu-id="155e4-109">Il `FindManifestResourceByName` metodo utilizza le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="155e4-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="155e4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="155e4-110">Requirements</span></span>  
 <span data-ttu-id="155e4-111">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="155e4-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="155e4-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="155e4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="155e4-113">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="155e4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="155e4-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="155e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155e4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155e4-115">See Also</span></span>  
 [<span data-ttu-id="155e4-116">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="155e4-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="155e4-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="155e4-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
