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
ms.openlocfilehash: ef6f7a1a6e86b45acce91792385bc3761dfb4c39
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009080"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="9dfd9-102">Metodo IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="9dfd9-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="9dfd9-103">Ottiene un puntatore alla risorsa del manifesto con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dfd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dfd9-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="9dfd9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dfd9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="9dfd9-106">[in] Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="9dfd9-107">out Matrice utilizzata per archiviare i `mdManifestResource` token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dfd9-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="9dfd9-108">Remarks</span></span>  
 <span data-ttu-id="9dfd9-109">Il `FindManifestResourceByName` metodo utilizza le regole standard utilizzate dal Common Language Runtime per la risoluzione dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="9dfd9-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dfd9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dfd9-110">Requirements</span></span>  
 <span data-ttu-id="9dfd9-111">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dfd9-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfd9-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9dfd9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9dfd9-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9dfd9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9dfd9-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfd9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfd9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dfd9-115">See also</span></span>

- [<span data-ttu-id="9dfd9-116">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9dfd9-116">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="9dfd9-117">Modalità di individuazione degli assembly da parte del runtime</span><span class="sxs-lookup"><span data-stu-id="9dfd9-117">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
