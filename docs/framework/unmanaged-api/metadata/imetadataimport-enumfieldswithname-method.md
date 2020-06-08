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
ms.openlocfilehash: 68261b165847a5c3ee29adbc4908451fb00c5443
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492265"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="0436a-102">Metodo IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="0436a-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="0436a-103">Enumera i token FieldDef del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0436a-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0436a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0436a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0436a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0436a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0436a-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0436a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="0436a-107">in Token del tipo i cui campi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="0436a-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="0436a-108">in Nome del campo che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0436a-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="0436a-109">out Matrice utilizzata per archiviare i token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="0436a-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0436a-110">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="0436a-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0436a-111">out Numero effettivo di token FieldDef restituiti in `rFields` .</span><span class="sxs-lookup"><span data-stu-id="0436a-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0436a-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0436a-112">Remarks</span></span>  
 <span data-ttu-id="0436a-113">A differenza di [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` Elimina tutti i token di campo che non hanno il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="0436a-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0436a-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0436a-114">Return Value</span></span>  
  
|<span data-ttu-id="0436a-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0436a-115">HRESULT</span></span>|<span data-ttu-id="0436a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0436a-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0436a-117">`EnumFieldsWithName`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0436a-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0436a-118">Nessun campo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0436a-118">There are no fields to enumerate.</span></span> <span data-ttu-id="0436a-119">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="0436a-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0436a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0436a-120">Requirements</span></span>  
 <span data-ttu-id="0436a-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0436a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0436a-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0436a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0436a-123">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0436a-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0436a-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0436a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0436a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0436a-125">See also</span></span>

- [<span data-ttu-id="0436a-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0436a-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0436a-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0436a-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
