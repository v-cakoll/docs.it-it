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
ms.openlocfilehash: ae9097725aecd21e910e49a78d81951df39e9b2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177769"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="fe36b-102">Metodo IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="fe36b-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="fe36b-103">Ottiene un puntatore alla risorsa di manifesto con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="fe36b-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe36b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe36b-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="fe36b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe36b-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fe36b-106">[in] Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="fe36b-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="fe36b-107">[fuori] Matrice utilizzata per `mdManifestResource` archiviare i token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.</span><span class="sxs-lookup"><span data-stu-id="fe36b-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe36b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fe36b-108">Remarks</span></span>  
 <span data-ttu-id="fe36b-109">Il `FindManifestResourceByName` metodo utilizza le regole standard utilizzate da Common Language Runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="fe36b-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe36b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe36b-110">Requirements</span></span>  
 <span data-ttu-id="fe36b-111">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe36b-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe36b-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe36b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe36b-113">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe36b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe36b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe36b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe36b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe36b-115">See also</span></span>

- [<span data-ttu-id="fe36b-116">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="fe36b-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fe36b-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="fe36b-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
