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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177567"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="940e1-102">Metodo IMetaDataEmit::SetClassLayout</span><span class="sxs-lookup"><span data-stu-id="940e1-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="940e1-103">Completa il layout dei campi per una classe definita da una precedente chiamata al metodo [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="940e1-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="940e1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="940e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="940e1-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="940e1-106">[in] Token `mdTypeDef` che specifica la classe da disporre.</span><span class="sxs-lookup"><span data-stu-id="940e1-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="940e1-107">[in] La dimensione di compressione: 1, 2, 4, 8 o 16 byte.</span><span class="sxs-lookup"><span data-stu-id="940e1-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="940e1-108">La dimensione di compressione è il numero di byte tra i campi adiacenti.</span><span class="sxs-lookup"><span data-stu-id="940e1-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="940e1-109">[in] Matrice di [strutture COR_FIELD_OFFSET,](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) ognuna delle quali specifica un campo della classe e l'offset del campo all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="940e1-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="940e1-110">Terminare la `mdTokenNil`matrice con .</span><span class="sxs-lookup"><span data-stu-id="940e1-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="940e1-111">[in] Dimensione, in byte, della classe.</span><span class="sxs-lookup"><span data-stu-id="940e1-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="940e1-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="940e1-112">Remarks</span></span>  
 <span data-ttu-id="940e1-113">La classe viene inizialmente definita chiamando il metodo [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito.</span><span class="sxs-lookup"><span data-stu-id="940e1-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="940e1-114">In genere, è necessario utilizzare il layout automatico e lasciare che il runtime scelga il modo migliore per definire il layout dei campi.</span><span class="sxs-lookup"><span data-stu-id="940e1-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="940e1-115">Tuttavia, è possibile che si desideri che i campi vengano disposti in base alla disposizione utilizzata dal codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="940e1-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="940e1-116">In questo caso, scegliere il layout `SetClassLayout` sequenziale o esplicito e chiamare per completare il layout dei campi:</span><span class="sxs-lookup"><span data-stu-id="940e1-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="940e1-117">Layout sequenziale: specificare le dimensioni di imballaggio.</span><span class="sxs-lookup"><span data-stu-id="940e1-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="940e1-118">Un campo viene allineato in base alle dimensioni naturali o alle dimensioni di imballaggio, a seconda dell'offset più piccolo del campo.</span><span class="sxs-lookup"><span data-stu-id="940e1-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="940e1-119">`rFieldOffsets` Impostare `ulClassSize` e a zero.</span><span class="sxs-lookup"><span data-stu-id="940e1-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="940e1-120">Layout esplicito: specificare l'offset di ogni campo o specificare la dimensione della classe e la dimensione di compressione.</span><span class="sxs-lookup"><span data-stu-id="940e1-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940e1-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="940e1-121">Requirements</span></span>  
 <span data-ttu-id="940e1-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="940e1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="940e1-123">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="940e1-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="940e1-124">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="940e1-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="940e1-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="940e1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940e1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="940e1-126">See also</span></span>

- [<span data-ttu-id="940e1-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="940e1-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="940e1-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="940e1-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
