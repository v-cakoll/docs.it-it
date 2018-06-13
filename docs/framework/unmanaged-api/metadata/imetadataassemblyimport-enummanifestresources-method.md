---
title: Metodo IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 707e482a6952ee1266950dc181fbc85e5d6ef398
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448055"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="29d32-102">Metodo IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="29d32-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="29d32-103">Ottiene un puntatore a un enumeratore per le risorse a cui fa riferimento nel manifesto dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="29d32-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29d32-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="29d32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29d32-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="29d32-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="29d32-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="29d32-107">Deve essere un valore null valore quando il `EnumManifestResources` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="29d32-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="29d32-108">[out] Matrice utilizzata per archiviare il `mdManifestResource` i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="29d32-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="29d32-109">[in] Il numero massimo di `mdManifestResource` i token che possono essere inseriti in `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="29d32-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="29d32-110">[out] Il numero di `mdManifestResource` token effettivamente inseriti in `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="29d32-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29d32-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="29d32-111">Return Value</span></span>  
  
|<span data-ttu-id="29d32-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29d32-112">HRESULT</span></span>|<span data-ttu-id="29d32-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29d32-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="29d32-114">`EnumManifestResources` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="29d32-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="29d32-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="29d32-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="29d32-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="29d32-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29d32-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29d32-117">Requirements</span></span>  
 <span data-ttu-id="29d32-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29d32-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29d32-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="29d32-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29d32-120">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="29d32-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29d32-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d32-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d32-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29d32-122">See Also</span></span>  
 [<span data-ttu-id="29d32-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="29d32-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
