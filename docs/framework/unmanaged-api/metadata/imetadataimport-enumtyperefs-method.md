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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de0fe4a51fbb49e80377b6b434bf3b72ddb90f02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081621"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="0a92e-102">Metodo IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="0a92e-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="0a92e-103">Enumera i token TypeRef definiti nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="0a92e-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a92e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a92e-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a92e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a92e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0a92e-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0a92e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0a92e-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="0a92e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="0a92e-108">[out] Matrice utilizzata per archiviare i token TypeRef.</span><span class="sxs-lookup"><span data-stu-id="0a92e-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0a92e-109">[in] Dimensione massima della matrice `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="0a92e-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="0a92e-110">[out] Un puntatore al numero di token TypeRef restituiti nel `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="0a92e-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a92e-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a92e-111">Return Value</span></span>  
  
|<span data-ttu-id="0a92e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a92e-112">HRESULT</span></span>|<span data-ttu-id="0a92e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a92e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0a92e-114">`EnumTypeRefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0a92e-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0a92e-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0a92e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0a92e-116">In tal caso, `pcTypeRefs` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="0a92e-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a92e-117">Note</span><span class="sxs-lookup"><span data-stu-id="0a92e-117">Remarks</span></span>  
 <span data-ttu-id="0a92e-118">Un token TypeRef rappresenta un riferimento a un tipo.</span><span class="sxs-lookup"><span data-stu-id="0a92e-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a92e-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a92e-119">Requirements</span></span>  
 <span data-ttu-id="0a92e-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a92e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a92e-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a92e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a92e-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0a92e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a92e-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a92e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a92e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a92e-124">See also</span></span>

- [<span data-ttu-id="0a92e-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0a92e-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0a92e-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0a92e-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
