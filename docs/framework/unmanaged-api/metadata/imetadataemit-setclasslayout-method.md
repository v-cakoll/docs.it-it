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
ms.openlocfilehash: a18583ce807ffa672811f3a0cd1e744233f6eb30
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008831"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="50dcc-102">Metodo IMetaDataEmit::SetClassLayout</span><span class="sxs-lookup"><span data-stu-id="50dcc-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="50dcc-103">Completa il layout dei campi per una classe definita da una chiamata precedente al [Metodo DefineTypeDef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="50dcc-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50dcc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50dcc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50dcc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50dcc-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="50dcc-106">in `mdTypeDef`Token che specifica la classe da disposte.</span><span class="sxs-lookup"><span data-stu-id="50dcc-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="50dcc-107">in Dimensioni di compressione: 1, 2, 4, 8 o 16 byte.</span><span class="sxs-lookup"><span data-stu-id="50dcc-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="50dcc-108">La dimensione di compressione è il numero di byte tra i campi adiacenti.</span><span class="sxs-lookup"><span data-stu-id="50dcc-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="50dcc-109">in Matrice di strutture di [COR_FIELD_OFFSET](cor-field-offset-structure.md) , ognuna delle quali specifica un campo della classe e l'offset del campo all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="50dcc-109">[in] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="50dcc-110">Terminare la matrice con `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="50dcc-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="50dcc-111">in Dimensione, in byte, della classe.</span><span class="sxs-lookup"><span data-stu-id="50dcc-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50dcc-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="50dcc-112">Remarks</span></span>  
 <span data-ttu-id="50dcc-113">La classe viene definita inizialmente chiamando il metodo [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito.</span><span class="sxs-lookup"><span data-stu-id="50dcc-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="50dcc-114">In genere, è possibile usare il layout automatico e consentire al runtime di scegliere il modo migliore per disporre i campi.</span><span class="sxs-lookup"><span data-stu-id="50dcc-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="50dcc-115">Tuttavia, è possibile che i campi siano disposti in base alla disposizione utilizzata dal codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="50dcc-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="50dcc-116">In questo caso, scegliere layout sequenziale o esplicito e chiamare `SetClassLayout` per completare il layout dei campi:</span><span class="sxs-lookup"><span data-stu-id="50dcc-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="50dcc-117">Layout sequenziale: specificare le dimensioni di compressione.</span><span class="sxs-lookup"><span data-stu-id="50dcc-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="50dcc-118">Un campo è allineato in base alla dimensione naturale o alla dimensione di compressione, a seconda del risultato dell'offset minore del campo.</span><span class="sxs-lookup"><span data-stu-id="50dcc-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="50dcc-119">Impostare `rFieldOffsets` e `ulClassSize` su zero.</span><span class="sxs-lookup"><span data-stu-id="50dcc-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="50dcc-120">Layout esplicito: specificare l'offset di ogni campo o specificare le dimensioni della classe e le dimensioni di compressione.</span><span class="sxs-lookup"><span data-stu-id="50dcc-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50dcc-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50dcc-121">Requirements</span></span>  
 <span data-ttu-id="50dcc-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50dcc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50dcc-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="50dcc-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50dcc-124">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50dcc-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50dcc-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50dcc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50dcc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50dcc-126">See also</span></span>

- [<span data-ttu-id="50dcc-127">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="50dcc-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="50dcc-128">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="50dcc-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
