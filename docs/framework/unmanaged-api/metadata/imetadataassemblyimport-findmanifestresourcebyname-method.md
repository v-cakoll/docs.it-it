---
title: Metodo IMetaDataAssemblyImport::FindManifestResourceByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9afc2ecc34131f62f1f8e8e86ca73f8b8b0126b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443512"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="be6c6-102">Metodo IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="be6c6-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="be6c6-103">Ottiene un puntatore alla risorsa di manifesto con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="be6c6-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be6c6-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="be6c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be6c6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="be6c6-106">[in] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="be6c6-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="be6c6-107">[out] Matrice utilizzata per archiviare il `mdManifestResource` i token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.</span><span class="sxs-lookup"><span data-stu-id="be6c6-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be6c6-108">Note</span><span class="sxs-lookup"><span data-stu-id="be6c6-108">Remarks</span></span>  
 <span data-ttu-id="be6c6-109">Il `FindManifestResourceByName` metodo utilizza le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="be6c6-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6c6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be6c6-110">Requirements</span></span>  
 <span data-ttu-id="be6c6-111">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be6c6-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6c6-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="be6c6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be6c6-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="be6c6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be6c6-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6c6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be6c6-115">See Also</span></span>  
 [<span data-ttu-id="be6c6-116">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="be6c6-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="be6c6-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="be6c6-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
