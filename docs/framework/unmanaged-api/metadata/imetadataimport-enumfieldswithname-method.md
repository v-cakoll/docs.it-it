---
title: Metodo IMetaDataImport::EnumFieldsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf624695136a9397937f05b28dec18493c8e12d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153660"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="f4dee-102">Metodo IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="f4dee-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="f4dee-103">Enumera i token FieldDef del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="f4dee-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4dee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4dee-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f4dee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4dee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f4dee-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="f4dee-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="f4dee-107">[in] Il token del tipo i cui campi sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f4dee-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="f4dee-108">[in] Il nome del campo che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f4dee-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="f4dee-109">[out] Matrice utilizzata per archiviare i token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="f4dee-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f4dee-110">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="f4dee-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f4dee-111">[out] Il numero effettivo di token FieldDef restituiti in `rFields`.</span><span class="sxs-lookup"><span data-stu-id="f4dee-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4dee-112">Note</span><span class="sxs-lookup"><span data-stu-id="f4dee-112">Remarks</span></span>  
 <span data-ttu-id="f4dee-113">A differenza [EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` ignora tutti i token di campo che non è il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="f4dee-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4dee-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f4dee-114">Return Value</span></span>  
  
|<span data-ttu-id="f4dee-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4dee-115">HRESULT</span></span>|<span data-ttu-id="f4dee-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4dee-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f4dee-117">`EnumFieldsWithName` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f4dee-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f4dee-118">Non sono presenti campi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="f4dee-118">There are no fields to enumerate.</span></span> <span data-ttu-id="f4dee-119">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="f4dee-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4dee-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4dee-120">Requirements</span></span>  
 <span data-ttu-id="f4dee-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4dee-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4dee-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4dee-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4dee-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f4dee-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4dee-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4dee-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dee-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4dee-125">See also</span></span>

- [<span data-ttu-id="f4dee-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f4dee-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f4dee-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f4dee-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
