---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e6314a76433276561a8b4b87a852464dae69824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656258"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="fad5d-102">Metodo IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="fad5d-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="fad5d-103">Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="fad5d-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fad5d-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fad5d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fad5d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fad5d-106">[out] Puntatore al nuovo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="fad5d-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="fad5d-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="fad5d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="fad5d-108">[in] Matrice utilizzata per archiviare i token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="fad5d-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fad5d-109">[in] Dimensione massima della matrice `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="fad5d-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="fad5d-110">[out] Il numero di token TypeDef restituiti in `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="fad5d-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fad5d-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fad5d-111">Return Value</span></span>  
  
|<span data-ttu-id="fad5d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fad5d-112">HRESULT</span></span>|<span data-ttu-id="fad5d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fad5d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fad5d-114">`EnumTypeDefs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fad5d-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fad5d-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="fad5d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fad5d-116">In tal caso, `pcTypeDefs` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="fad5d-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fad5d-117">Note</span><span class="sxs-lookup"><span data-stu-id="fad5d-117">Remarks</span></span>  
 <span data-ttu-id="fad5d-118">Il token TypeDef rappresenta un tipo, ad esempio una classe o un'interfaccia, nonché qualsiasi tipo aggiunto tramite un meccanismo di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="fad5d-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad5d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fad5d-119">Requirements</span></span>  
 <span data-ttu-id="fad5d-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad5d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad5d-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fad5d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fad5d-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fad5d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fad5d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad5d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad5d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad5d-124">See also</span></span>
- [<span data-ttu-id="fad5d-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fad5d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fad5d-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fad5d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
