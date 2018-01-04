---
title: Metodo IMetaDataImport::EnumFieldsWithName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumFieldsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77b5ba7e191d9aa0f1587e4ac1ec25e655c27b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="0a8d2-102">Metodo IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="0a8d2-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="0a8d2-103">Enumera i token FieldDef del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a8d2-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a8d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a8d2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0a8d2-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="0a8d2-107">[in] Il token del tipo i cui campi sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="0a8d2-108">[in] Il nome del campo che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="0a8d2-109">[out] Matrice utilizzata per archiviare i token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0a8d2-110">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0a8d2-111">[out] Il numero effettivo di token FieldDef restituiti in `rFields`.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a8d2-112">Note</span><span class="sxs-lookup"><span data-stu-id="0a8d2-112">Remarks</span></span>  
 <span data-ttu-id="0a8d2-113">A differenza di [IMetaDataImport:: EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` ignora tutti i token di campo che non contengono il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a8d2-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a8d2-114">Return Value</span></span>  
  
|<span data-ttu-id="0a8d2-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a8d2-115">HRESULT</span></span>|<span data-ttu-id="0a8d2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a8d2-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0a8d2-117">`EnumFieldsWithName`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0a8d2-118">Non sono presenti campi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-118">There are no fields to enumerate.</span></span> <span data-ttu-id="0a8d2-119">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="0a8d2-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a8d2-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a8d2-120">Requirements</span></span>  
 <span data-ttu-id="0a8d2-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a8d2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a8d2-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a8d2-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a8d2-123">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a8d2-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a8d2-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a8d2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8d2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a8d2-125">See Also</span></span>  
 [<span data-ttu-id="0a8d2-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0a8d2-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0a8d2-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0a8d2-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
