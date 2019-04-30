---
title: Metodo IMetaDataImport2::GetGenericParamConstraintProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0503c5bd924793df8143c89e358618fb8844c6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049869"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="d7f01-102">Metodo IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="d7f01-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="d7f01-103">Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.</span><span class="sxs-lookup"><span data-stu-id="d7f01-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f01-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7f01-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f01-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7f01-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="d7f01-106">[in] Il token al vincolo del parametro generico per il quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="d7f01-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="d7f01-107">[out] Puntatore al token che rappresenta il parametro generico che è vincolato.</span><span class="sxs-lookup"><span data-stu-id="d7f01-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="d7f01-108">[out] Un puntatore a un token TypeDef, TypeRef o TypeSpec che rappresenta un vincolo su `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="d7f01-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f01-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7f01-109">Requirements</span></span>  
 <span data-ttu-id="d7f01-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f01-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f01-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d7f01-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7f01-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d7f01-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7f01-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f01-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f01-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7f01-114">See also</span></span>

- [<span data-ttu-id="d7f01-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d7f01-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d7f01-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d7f01-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
