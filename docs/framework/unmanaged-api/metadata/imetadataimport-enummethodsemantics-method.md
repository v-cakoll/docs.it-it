---
title: Metodo IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491914"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="603d3-102">Metodo IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="603d3-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="603d3-103">Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="603d3-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="603d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="603d3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="603d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="603d3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="603d3-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="603d3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="603d3-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="603d3-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="603d3-108">in Token MethodDef che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="603d3-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="603d3-109">out Matrice utilizzata per archiviare gli eventi o le proprietà.</span><span class="sxs-lookup"><span data-stu-id="603d3-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="603d3-110">[in] Dimensione massima della matrice `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="603d3-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="603d3-111">out Numero di eventi o proprietà restituiti in `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="603d3-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="603d3-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="603d3-112">Return Value</span></span>  
  
|<span data-ttu-id="603d3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="603d3-113">HRESULT</span></span>|<span data-ttu-id="603d3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="603d3-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="603d3-115">`EnumMethodSemantics`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="603d3-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="603d3-116">Nessun evento o proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="603d3-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="603d3-117">In tal caso, `pcEventProp` è zero.</span><span class="sxs-lookup"><span data-stu-id="603d3-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="603d3-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="603d3-118">Remarks</span></span>  
 <span data-ttu-id="603d3-119">Molti tipi di Common Language Runtime *definiscono* `Changed` gli eventi e `On` *Property* `Changed` i metodi delle proprietà correlati alle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="603d3-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="603d3-120">Il tipo, ad esempio, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> definisce una <xref:System.Windows.Forms.Control.Font%2A> proprietà, un <xref:System.Windows.Forms.Control.FontChanged> evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="603d3-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="603d3-121">Il metodo della funzione di accesso set della <xref:System.Windows.Forms.Control.Font%2A> proprietà chiama il <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera l' <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="603d3-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="603d3-122">È possibile chiamare `EnumMethodSemantics` utilizzando MethodDef per per <xref:System.Windows.Forms.Control.OnFontChanged%2A> ottenere riferimenti alla <xref:System.Windows.Forms.Control.Font%2A> proprietà e all' <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="603d3-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="603d3-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="603d3-123">Requirements</span></span>  
 <span data-ttu-id="603d3-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="603d3-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="603d3-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="603d3-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="603d3-126">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="603d3-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="603d3-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="603d3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603d3-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="603d3-128">See also</span></span>

- [<span data-ttu-id="603d3-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="603d3-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="603d3-130">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="603d3-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
