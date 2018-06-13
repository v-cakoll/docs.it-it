---
title: Metodo IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a56d874e5e7ef491c24b0aef2ace700087de677
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447411"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="77422-102">Metodo IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="77422-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="77422-103">Enumera il `mdAssemblyRef` istanze definite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="77422-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77422-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77422-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77422-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77422-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="77422-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="77422-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="77422-107">Deve essere un valore null valore quando il `EnumAssemblyRefs` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="77422-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="77422-108">[out] L'enumerazione di `mdAssemblyRef` i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="77422-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="77422-109">[in] Il numero massimo di token che può essere inserita nel `rAssemblyRefs` matrice.</span><span class="sxs-lookup"><span data-stu-id="77422-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="77422-110">[out] Numero di token effettivamente inseriti in `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="77422-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77422-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77422-111">Return Value</span></span>  
  
|<span data-ttu-id="77422-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77422-112">HRESULT</span></span>|<span data-ttu-id="77422-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77422-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="77422-114">`EnumAssemblyRefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="77422-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="77422-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="77422-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="77422-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="77422-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77422-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77422-117">Requirements</span></span>  
 <span data-ttu-id="77422-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77422-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77422-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77422-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77422-120">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="77422-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77422-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77422-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77422-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77422-122">See Also</span></span>  
 [<span data-ttu-id="77422-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="77422-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
