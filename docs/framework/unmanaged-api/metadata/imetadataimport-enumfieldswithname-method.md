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
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177347"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="5b4a9-102">Metodo IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="5b4a9-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="5b4a9-103">Enumera i token FieldDef del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b4a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b4a9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b4a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b4a9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5b4a9-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="5b4a9-107">[in] Token del tipo i cui campi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="5b4a9-108">[in] Nome di campo che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="5b4a9-109">[fuori] Matrice utilizzata per archiviare i token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5b4a9-110">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5b4a9-111">[fuori] Numero effettivo di token FieldDef `rFields`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="5b4a9-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b4a9-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5b4a9-112">Remarks</span></span>  
 <span data-ttu-id="5b4a9-113">A differenza di [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` elimina tutti i token di campo che non hanno il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b4a9-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b4a9-114">Return Value</span></span>  
  
|<span data-ttu-id="5b4a9-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b4a9-115">HRESULT</span></span>|<span data-ttu-id="5b4a9-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b4a9-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5b4a9-117">`EnumFieldsWithName`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5b4a9-118">Non sono presenti campi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-118">There are no fields to enumerate.</span></span> <span data-ttu-id="5b4a9-119">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="5b4a9-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b4a9-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b4a9-120">Requirements</span></span>  
 <span data-ttu-id="5b4a9-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b4a9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b4a9-122">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b4a9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b4a9-123">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b4a9-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b4a9-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b4a9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4a9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b4a9-125">See also</span></span>

- [<span data-ttu-id="5b4a9-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5b4a9-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5b4a9-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5b4a9-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
