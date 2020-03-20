---
title: Metodo IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175811"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="fde83-102">Metodo IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="fde83-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="fde83-103">Crea la firma dei metadati `mdTypeDef` di una definizione di tipo, restituisce un token per tale `tdEncloser` tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il parametro.</span><span class="sxs-lookup"><span data-stu-id="fde83-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde83-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fde83-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fde83-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fde83-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="fde83-106">[in] Nome del tipo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="fde83-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="fde83-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="fde83-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="fde83-108">Si tratta di `CorTypeAttr` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="fde83-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="fde83-109">[in] Token della classe base.</span><span class="sxs-lookup"><span data-stu-id="fde83-109">[in] The token of the base class.</span></span> <span data-ttu-id="fde83-110">Si tratta `mdTypeDef` di `mdTypeRef` un o un token.</span><span class="sxs-lookup"><span data-stu-id="fde83-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="fde83-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="fde83-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="fde83-112">[in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fde83-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="fde83-113">[in] Token del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="fde83-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="fde83-114">L'ultimo elemento della `mdTokenNil`matrice deve essere .</span><span class="sxs-lookup"><span data-stu-id="fde83-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="fde83-115">[fuori] Token `mdTypeDef` assegnato.</span><span class="sxs-lookup"><span data-stu-id="fde83-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde83-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fde83-116">Requirements</span></span>  
 <span data-ttu-id="fde83-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fde83-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde83-118">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fde83-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fde83-119">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fde83-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fde83-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde83-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde83-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fde83-121">See also</span></span>

- [<span data-ttu-id="fde83-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fde83-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fde83-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fde83-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
