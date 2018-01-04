---
title: Metodo IMetaDataImport2::GetGenericParamConstraintProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamConstraintProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c860c4f2bf1991ca929d82ef3dec61f5d20a57d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="549d4-102">Metodo IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="549d4-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="549d4-103">Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.</span><span class="sxs-lookup"><span data-stu-id="549d4-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="549d4-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="549d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="549d4-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="549d4-106">[in] Il token al vincolo del parametro generico per il quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="549d4-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="549d4-107">[out] Puntatore al token che rappresenta il parametro generico che è vincolato.</span><span class="sxs-lookup"><span data-stu-id="549d4-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="549d4-108">[out] Un puntatore a un token TypeDef o TypeRef TypeSpec che rappresenta un vincolo su `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="549d4-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="549d4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="549d4-109">Requirements</span></span>  
 <span data-ttu-id="549d4-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="549d4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="549d4-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="549d4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="549d4-112">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="549d4-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="549d4-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="549d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549d4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="549d4-114">See Also</span></span>  
 [<span data-ttu-id="549d4-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="549d4-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="549d4-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="549d4-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
