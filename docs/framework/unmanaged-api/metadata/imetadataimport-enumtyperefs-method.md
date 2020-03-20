---
title: Metodo IMetaDataImport::EnumTypeRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175434"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="8a330-102">Metodo IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="8a330-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="8a330-103">Enumera i token TypeRef definiti nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="8a330-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a330-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a330-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a330-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a330-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8a330-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="8a330-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8a330-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8a330-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="8a330-108">[fuori] Matrice utilizzata per archiviare i token TypeRef.</span><span class="sxs-lookup"><span data-stu-id="8a330-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8a330-109">[in] Dimensione massima della matrice `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="8a330-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="8a330-110">[fuori] Puntatore al numero di token TypeRef `rTypeRefs`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="8a330-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a330-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a330-111">Return Value</span></span>  
  
|<span data-ttu-id="8a330-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a330-112">HRESULT</span></span>|<span data-ttu-id="8a330-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a330-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a330-114">`EnumTypeRefs`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="8a330-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8a330-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="8a330-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8a330-116">In tal `pcTypeRefs` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="8a330-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a330-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8a330-117">Remarks</span></span>  
 <span data-ttu-id="8a330-118">Un token TypeRef rappresenta un riferimento a un tipo.</span><span class="sxs-lookup"><span data-stu-id="8a330-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a330-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a330-119">Requirements</span></span>  
 <span data-ttu-id="8a330-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a330-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a330-121">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a330-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a330-122">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a330-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a330-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a330-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a330-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a330-124">See also</span></span>

- [<span data-ttu-id="8a330-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8a330-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8a330-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8a330-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
