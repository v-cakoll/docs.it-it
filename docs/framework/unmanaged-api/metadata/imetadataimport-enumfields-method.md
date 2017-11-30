---
title: Metodo IMetaDataImport::EnumFields
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumFields
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 90cfe65779ec71ae483f1119e30bbc4c7e3ec4cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="457a7-102">Metodo IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="457a7-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="457a7-103">Enumera i token FieldDef per il tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="457a7-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="457a7-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="457a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="457a7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="457a7-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="457a7-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="457a7-107">[in] Il token TypeDef della classe i cui campi sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="457a7-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="457a7-108">[out] Elenco di token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="457a7-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="457a7-109">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="457a7-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="457a7-110">[out] Il numero effettivo di token FieldDef restituiti in `rFields`.</span><span class="sxs-lookup"><span data-stu-id="457a7-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="457a7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="457a7-111">Return Value</span></span>  
  
|<span data-ttu-id="457a7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="457a7-112">HRESULT</span></span>|<span data-ttu-id="457a7-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="457a7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="457a7-114">`EnumFields`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="457a7-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="457a7-115">Non sono presenti campi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="457a7-115">There are no fields to enumerate.</span></span> <span data-ttu-id="457a7-116">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="457a7-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="457a7-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="457a7-117">Requirements</span></span>  
 <span data-ttu-id="457a7-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="457a7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457a7-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="457a7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="457a7-120">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="457a7-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="457a7-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457a7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457a7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="457a7-122">See Also</span></span>  
 [<span data-ttu-id="457a7-123">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="457a7-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="457a7-124">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="457a7-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
