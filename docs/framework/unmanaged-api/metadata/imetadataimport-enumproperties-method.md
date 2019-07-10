---
title: Metodo IMetaDataImport::EnumProperties
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c63797b60354b461891f44d32cf1840f7fdcf3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756487"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="1610a-102">Metodo IMetaDataImport::EnumProperties</span><span class="sxs-lookup"><span data-stu-id="1610a-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="1610a-103">Enumera i token PropertyDef che rappresentano le proprietà del tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="1610a-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1610a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1610a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1610a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1610a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1610a-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="1610a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1610a-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="1610a-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="1610a-108">[in] Token TypeDef che rappresenta il tipo con le proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="1610a-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="1610a-109">[out] Matrice utilizzata per archiviare i token PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="1610a-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1610a-110">[in] Dimensione massima della matrice `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="1610a-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="1610a-111">[out] Il numero di token PropertyDef restituiti in `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="1610a-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1610a-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1610a-112">Return Value</span></span>  
  
|<span data-ttu-id="1610a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1610a-113">HRESULT</span></span>|<span data-ttu-id="1610a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1610a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1610a-115">`EnumProperties` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1610a-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1610a-116">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="1610a-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="1610a-117">In tal caso, `pcProperties` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="1610a-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1610a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1610a-118">Requirements</span></span>  
 <span data-ttu-id="1610a-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1610a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1610a-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1610a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1610a-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1610a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1610a-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1610a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1610a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1610a-123">See also</span></span>

- [<span data-ttu-id="1610a-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1610a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1610a-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1610a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
