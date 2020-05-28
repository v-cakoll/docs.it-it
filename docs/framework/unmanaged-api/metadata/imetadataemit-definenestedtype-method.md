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
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004355"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="d3cf9-102">Metodo IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="d3cf9-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="d3cf9-103">Crea la firma dei metadati di una definizione di tipo, restituisce un `mdTypeDef` token per quel tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il `tdEncloser` parametro.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3cf9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3cf9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d3cf9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3cf9-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="d3cf9-106">in Nome del tipo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="d3cf9-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="d3cf9-108">Si tratta di una maschera di maschera di `CorTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="d3cf9-109">in Token della classe di base.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-109">[in] The token of the base class.</span></span> <span data-ttu-id="d3cf9-110">Si tratta di un `mdTypeDef` token o `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="d3cf9-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="d3cf9-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="d3cf9-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="d3cf9-112">in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="d3cf9-113">in Token del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="d3cf9-114">L'ultimo elemento della matrice deve essere `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="d3cf9-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="d3cf9-115">out `mdTypeDef`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="d3cf9-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3cf9-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3cf9-116">Requirements</span></span>  
 <span data-ttu-id="d3cf9-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3cf9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3cf9-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3cf9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3cf9-119">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3cf9-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3cf9-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3cf9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3cf9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3cf9-121">See also</span></span>

- [<span data-ttu-id="d3cf9-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d3cf9-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d3cf9-123">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d3cf9-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
