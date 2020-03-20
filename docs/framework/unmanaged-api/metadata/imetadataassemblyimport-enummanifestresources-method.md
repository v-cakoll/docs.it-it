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
ms.openlocfilehash: 22141cf46a965c0624c076bd1d86d2624e5a09f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176019"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="f3281-102">Metodo IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="f3281-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="f3281-103">Ottiene un puntatore a un enumeratore per le risorse a cui viene fatto riferimento nel manifesto dell'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="f3281-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3281-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3281-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="f3281-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3281-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f3281-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="f3281-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f3281-107">Deve essere un valore `EnumManifestResources` null quando il metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="f3281-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="f3281-108">[fuori] Matrice utilizzata per `mdManifestResource` archiviare i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="f3281-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f3281-109">[in] Numero massimo `mdManifestResource` di token che possono `rManifestResources`essere inseriti in .</span><span class="sxs-lookup"><span data-stu-id="f3281-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f3281-110">[fuori] Il numero `mdManifestResource` di token `rManifestResources`effettivamente inseriti in .</span><span class="sxs-lookup"><span data-stu-id="f3281-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3281-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3281-111">Return Value</span></span>  
  
|<span data-ttu-id="f3281-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3281-112">HRESULT</span></span>|<span data-ttu-id="f3281-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3281-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f3281-114">`EnumManifestResources`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="f3281-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f3281-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f3281-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f3281-116">In questo `pcTokens` caso, è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="f3281-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3281-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3281-117">Requirements</span></span>  
 <span data-ttu-id="f3281-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3281-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3281-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f3281-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3281-120">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3281-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3281-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3281-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3281-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3281-122">See also</span></span>

- [<span data-ttu-id="f3281-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="f3281-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
