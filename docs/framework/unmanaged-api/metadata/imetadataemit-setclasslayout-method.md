---
title: Metodo IMetaDataEmit::SetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: 5214298c6ad9594548ab45ed583cb5b14ce1f30d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441769"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="b3b41-102">Metodo IMetaDataEmit::SetClassLayout</span><span class="sxs-lookup"><span data-stu-id="b3b41-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="b3b41-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b3b41-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3b41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3b41-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3b41-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3b41-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b3b41-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span><span class="sxs-lookup"><span data-stu-id="b3b41-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="b3b41-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="b3b41-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="b3b41-108">The packing size is the number of bytes between adjacent fields.</span><span class="sxs-lookup"><span data-stu-id="b3b41-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="b3b41-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span><span class="sxs-lookup"><span data-stu-id="b3b41-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="b3b41-110">Terminate the array with `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="b3b41-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="b3b41-111">[in] The size, in bytes, of the class.</span><span class="sxs-lookup"><span data-stu-id="b3b41-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3b41-112">Note</span><span class="sxs-lookup"><span data-stu-id="b3b41-112">Remarks</span></span>  
 <span data-ttu-id="b3b41-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span><span class="sxs-lookup"><span data-stu-id="b3b41-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="b3b41-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span><span class="sxs-lookup"><span data-stu-id="b3b41-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="b3b41-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span><span class="sxs-lookup"><span data-stu-id="b3b41-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="b3b41-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span><span class="sxs-lookup"><span data-stu-id="b3b41-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="b3b41-117">Sequential layout: Specify the packing size.</span><span class="sxs-lookup"><span data-stu-id="b3b41-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="b3b41-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span><span class="sxs-lookup"><span data-stu-id="b3b41-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="b3b41-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span><span class="sxs-lookup"><span data-stu-id="b3b41-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="b3b41-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span><span class="sxs-lookup"><span data-stu-id="b3b41-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3b41-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3b41-121">Requirements</span></span>  
 <span data-ttu-id="b3b41-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3b41-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3b41-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3b41-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3b41-124">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3b41-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3b41-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3b41-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3b41-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3b41-126">See also</span></span>

- [<span data-ttu-id="b3b41-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b3b41-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b3b41-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b3b41-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
