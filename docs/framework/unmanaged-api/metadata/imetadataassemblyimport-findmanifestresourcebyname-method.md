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
ms.openlocfilehash: bf61da362251577acadb83915404eba7508b3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141570"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="023cf-102">Metodo IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="023cf-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="023cf-103">Ottiene un puntatore alla risorsa di manifesto con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="023cf-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="023cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="023cf-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="023cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="023cf-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="023cf-106">[in] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="023cf-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="023cf-107">[out] La matrice utilizzata per archiviare il `mdManifestResource` i token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.</span><span class="sxs-lookup"><span data-stu-id="023cf-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="023cf-108">Note</span><span class="sxs-lookup"><span data-stu-id="023cf-108">Remarks</span></span>  
 <span data-ttu-id="023cf-109">Il `FindManifestResourceByName` metodo Usa le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="023cf-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023cf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="023cf-110">Requirements</span></span>  
 <span data-ttu-id="023cf-111">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="023cf-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023cf-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="023cf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="023cf-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="023cf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="023cf-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="023cf-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="023cf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="023cf-115">See also</span></span>

- [<span data-ttu-id="023cf-116">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="023cf-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="023cf-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="023cf-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
