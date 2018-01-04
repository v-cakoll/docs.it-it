---
title: Metodo IMetaDataImport::EnumParams
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51544a44ed4bae25d4214e25c717769a8446f0f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="bdf73-102">Metodo IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="bdf73-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="bdf73-103">Enumera i token ParamDef che rappresentano i parametri del metodo a cui fa riferimento il token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="bdf73-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdf73-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdf73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdf73-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bdf73-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="bdf73-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bdf73-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="bdf73-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="bdf73-108">[in] Token MethodDef che rappresenta il metodo con i parametri da enumerare.</span><span class="sxs-lookup"><span data-stu-id="bdf73-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="bdf73-109">[out] Matrice utilizzata per archiviare i token ParamDef.</span><span class="sxs-lookup"><span data-stu-id="bdf73-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bdf73-110">[in] Dimensione massima della matrice `rParams`.</span><span class="sxs-lookup"><span data-stu-id="bdf73-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bdf73-111">[out] Il numero di token ParamDef restituiti in `rParams`.</span><span class="sxs-lookup"><span data-stu-id="bdf73-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdf73-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bdf73-112">Return Value</span></span>  
  
|<span data-ttu-id="bdf73-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdf73-113">HRESULT</span></span>|<span data-ttu-id="bdf73-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdf73-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bdf73-115">`EnumParams`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="bdf73-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bdf73-116">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="bdf73-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="bdf73-117">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="bdf73-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdf73-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdf73-118">Requirements</span></span>  
 <span data-ttu-id="bdf73-119">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf73-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf73-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bdf73-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdf73-121">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdf73-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdf73-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf73-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf73-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdf73-123">See Also</span></span>  
 [<span data-ttu-id="bdf73-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bdf73-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bdf73-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bdf73-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
