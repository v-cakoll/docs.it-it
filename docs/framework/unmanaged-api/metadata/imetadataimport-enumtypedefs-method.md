---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeDefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a07d9ff237e6d3838fffb068e3a9ebf9febf66fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="b9853-102">Metodo IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="b9853-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="b9853-103">Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="b9853-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9853-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9853-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9853-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9853-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b9853-106">[out] Un puntatore per il nuovo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b9853-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="b9853-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="b9853-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="b9853-108">[in] Matrice utilizzata per archiviare i token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="b9853-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b9853-109">[in] Dimensione massima della matrice `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="b9853-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="b9853-110">[out] Il numero di token TypeDef restituiti in `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="b9853-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9853-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9853-111">Return Value</span></span>  
  
|<span data-ttu-id="b9853-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9853-112">HRESULT</span></span>|<span data-ttu-id="b9853-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9853-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b9853-114">`EnumTypeDefs`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b9853-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b9853-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="b9853-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b9853-116">In tal caso, `pcTypeDefs` è zero.</span><span class="sxs-lookup"><span data-stu-id="b9853-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9853-117">Note</span><span class="sxs-lookup"><span data-stu-id="b9853-117">Remarks</span></span>  
 <span data-ttu-id="b9853-118">Il token TypeDef rappresenta un tipo, ad esempio una classe o un'interfaccia, come qualsiasi tipo aggiunto tramite un meccanismo di extensibility.</span><span class="sxs-lookup"><span data-stu-id="b9853-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9853-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9853-119">Requirements</span></span>  
 <span data-ttu-id="b9853-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9853-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9853-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9853-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9853-122">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9853-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9853-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9853-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9853-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9853-124">See Also</span></span>  
 [<span data-ttu-id="b9853-125">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b9853-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b9853-126">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b9853-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
