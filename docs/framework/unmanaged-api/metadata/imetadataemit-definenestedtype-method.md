---
title: Metodo IMetaDataEmit::DefineNestedType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineNestedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99250d98f9ffd90857128aa5d8a675a997926bf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="ff251-102">Metodo IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="ff251-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="ff251-103">Crea la firma dei metadati di una definizione di tipo, restituisce un `mdTypeDef` token per il tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il `tdEncloser` parametro.</span><span class="sxs-lookup"><span data-stu-id="ff251-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff251-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff251-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff251-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff251-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="ff251-106">[in] Il nome del tipo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff251-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="ff251-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="ff251-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="ff251-108">Si tratta di una maschera di bit di `CorTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="ff251-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="ff251-109">[in] Il token della classe di base.</span><span class="sxs-lookup"><span data-stu-id="ff251-109">[in] The token of the base class.</span></span> <span data-ttu-id="ff251-110">Questo è un `mdTypeDef` o `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="ff251-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="ff251-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="ff251-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="ff251-112">[in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ff251-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="ff251-113">[in] Il token del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ff251-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="ff251-114">L'ultimo elemento della matrice deve essere `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="ff251-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="ff251-115">[out] Il `mdTypeDef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="ff251-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff251-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff251-116">Requirements</span></span>  
 <span data-ttu-id="ff251-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff251-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff251-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff251-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff251-119">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff251-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff251-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff251-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff251-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff251-121">See Also</span></span>  
 [<span data-ttu-id="ff251-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ff251-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ff251-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ff251-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
