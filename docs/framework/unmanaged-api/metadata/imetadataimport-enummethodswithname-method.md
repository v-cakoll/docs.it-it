---
title: Metodo IMetaDataImport::EnumMethodsWithName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f16e66f83925104c4be1e69a476e398f33295a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="6ef24-102">Metodo IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="6ef24-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="6ef24-103">Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="6ef24-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ef24-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ef24-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ef24-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6ef24-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="6ef24-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6ef24-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="6ef24-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="6ef24-108">[in] Token TypeDef che rappresenta il tipo i cui metodi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="6ef24-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="6ef24-109">[in] Il nome che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6ef24-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="6ef24-110">[out] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="6ef24-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6ef24-111">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="6ef24-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6ef24-112">[out] Il numero di token MethodDef restituiti in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="6ef24-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef24-113">Note</span><span class="sxs-lookup"><span data-stu-id="6ef24-113">Remarks</span></span>  
 <span data-ttu-id="6ef24-114">Questo metodo enumera i campi e metodi, ma non a proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="6ef24-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="6ef24-115">A differenza di [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` Elimina tutti i token che non contengono il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="6ef24-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ef24-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ef24-116">Return Value</span></span>  
  
|<span data-ttu-id="6ef24-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ef24-117">HRESULT</span></span>|<span data-ttu-id="6ef24-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ef24-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6ef24-119">`EnumMethodsWithName`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6ef24-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6ef24-120">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="6ef24-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="6ef24-121">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="6ef24-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ef24-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ef24-122">Requirements</span></span>  
 <span data-ttu-id="6ef24-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef24-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6ef24-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ef24-125">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ef24-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ef24-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef24-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef24-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ef24-127">See Also</span></span>  
 [<span data-ttu-id="6ef24-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6ef24-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6ef24-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6ef24-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
