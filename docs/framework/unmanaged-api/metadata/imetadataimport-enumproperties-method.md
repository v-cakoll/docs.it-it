---
title: Metodo IMetaDataImport::EnumProperties
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumProperties
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d46e18707ff6b34e32a73aed81c2b7e57f769ed6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="893dc-102">Metodo IMetaDataImport::EnumProperties</span><span class="sxs-lookup"><span data-stu-id="893dc-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="893dc-103">Enumera i token PropertyDef che rappresentano le proprietà del tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="893dc-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="893dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="893dc-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="893dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="893dc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="893dc-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="893dc-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="893dc-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="893dc-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="893dc-108">[in] Token TypeDef che rappresenta il tipo con le proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="893dc-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="893dc-109">[out] Matrice utilizzata per archiviare i token PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="893dc-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="893dc-110">[in] Dimensione massima della matrice `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="893dc-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="893dc-111">[out] Il numero di token PropertyDef restituiti in `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="893dc-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="893dc-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="893dc-112">Return Value</span></span>  
  
|<span data-ttu-id="893dc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="893dc-113">HRESULT</span></span>|<span data-ttu-id="893dc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="893dc-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="893dc-115">`EnumProperties`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="893dc-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="893dc-116">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="893dc-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="893dc-117">In tal caso, `pcProperties` è zero.</span><span class="sxs-lookup"><span data-stu-id="893dc-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="893dc-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="893dc-118">Requirements</span></span>  
 <span data-ttu-id="893dc-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="893dc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="893dc-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="893dc-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="893dc-121">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="893dc-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="893dc-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="893dc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893dc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="893dc-123">See Also</span></span>  
 [<span data-ttu-id="893dc-124">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="893dc-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="893dc-125">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="893dc-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
