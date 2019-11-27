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
ms.openlocfilehash: b240be3e5b0127de42cea43dd8e89a2cc656b28e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449520"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="4f81f-102">Metodo IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="4f81f-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="4f81f-103">Enumera i token FieldDef del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4f81f-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f81f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f81f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4f81f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f81f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4f81f-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="4f81f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="4f81f-107">in Token del tipo i cui campi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="4f81f-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f81f-108">in Nome del campo che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f81f-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="4f81f-109">out Matrice utilizzata per archiviare i token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="4f81f-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4f81f-110">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="4f81f-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4f81f-111">out Numero effettivo di token FieldDef restituiti in `rFields`.</span><span class="sxs-lookup"><span data-stu-id="4f81f-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f81f-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4f81f-112">Remarks</span></span>  
 <span data-ttu-id="4f81f-113">A differenza di [IMetaDataImport:: EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` Elimina tutti i token di campo che non hanno il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4f81f-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f81f-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f81f-114">Return Value</span></span>  
  
|<span data-ttu-id="4f81f-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f81f-115">HRESULT</span></span>|<span data-ttu-id="4f81f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f81f-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4f81f-117">`EnumFieldsWithName` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4f81f-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4f81f-118">Nessun campo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="4f81f-118">There are no fields to enumerate.</span></span> <span data-ttu-id="4f81f-119">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="4f81f-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f81f-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f81f-120">Requirements</span></span>  
 <span data-ttu-id="4f81f-121">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f81f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f81f-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f81f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f81f-123">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4f81f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f81f-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f81f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f81f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f81f-125">See also</span></span>

- [<span data-ttu-id="4f81f-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4f81f-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4f81f-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4f81f-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
