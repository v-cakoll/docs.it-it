---
title: Metodo IMetaDataImport::EnumFields
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: be2845d1d660d86447cfbb6f2845a8e68b727e66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175512"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="dd02c-102">Metodo IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="dd02c-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="dd02c-103">Enumera i token FieldDef per il tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="dd02c-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd02c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd02c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd02c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd02c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dd02c-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="dd02c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="dd02c-107">[in] Token TypeDef della classe i cui campi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="dd02c-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="dd02c-108">[fuori] Elenco di token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="dd02c-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dd02c-109">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="dd02c-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="dd02c-110">[fuori] Numero effettivo di token FieldDef `rFields`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="dd02c-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd02c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd02c-111">Return Value</span></span>  
  
|<span data-ttu-id="dd02c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd02c-112">HRESULT</span></span>|<span data-ttu-id="dd02c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd02c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dd02c-114">`EnumFields`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="dd02c-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dd02c-115">Non sono presenti campi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="dd02c-115">There are no fields to enumerate.</span></span> <span data-ttu-id="dd02c-116">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="dd02c-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd02c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd02c-117">Requirements</span></span>  
 <span data-ttu-id="dd02c-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd02c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd02c-119">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd02c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd02c-120">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd02c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd02c-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd02c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd02c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd02c-122">See also</span></span>

- [<span data-ttu-id="dd02c-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="dd02c-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dd02c-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="dd02c-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
