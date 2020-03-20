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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175460"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="bb8b1-102">Metodo IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="bb8b1-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="bb8b1-103">Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb8b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb8b1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb8b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb8b1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bb8b1-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bb8b1-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="bb8b1-108">[in] Token MethodDef che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="bb8b1-109">[fuori] Matrice utilizzata per archiviare gli eventi o le proprietà.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bb8b1-110">[in] Dimensione massima della matrice `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="bb8b1-111">[fuori] Numero di eventi o proprietà `rEventProp`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="bb8b1-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb8b1-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb8b1-112">Return Value</span></span>  
  
|<span data-ttu-id="bb8b1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb8b1-113">HRESULT</span></span>|<span data-ttu-id="bb8b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb8b1-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bb8b1-115">`EnumMethodSemantics`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bb8b1-116">Non sono presenti eventi o proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="bb8b1-117">In tal `pcEventProp` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb8b1-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bb8b1-118">Remarks</span></span>  
 <span data-ttu-id="bb8b1-119">Molti tipi di Common Language `On`Runtime definiscono gli eventi *Property* `Changed` e i metodi *Property* `Changed` correlati alle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="bb8b1-120">Ad esempio, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> il tipo <xref:System.Windows.Forms.Control.Font%2A> definisce <xref:System.Windows.Forms.Control.FontChanged> una proprietà, un evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="bb8b1-121">Il metodo della funzione <xref:System.Windows.Forms.Control.Font%2A> di <xref:System.Windows.Forms.Control.OnFontChanged%2A> accesso set della <xref:System.Windows.Forms.Control.FontChanged> proprietà chiama il metodo, che a sua volta genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="bb8b1-122">È necessario `EnumMethodSemantics` chiamare utilizzando <xref:System.Windows.Forms.Control.OnFontChanged%2A> MethodDef per <xref:System.Windows.Forms.Control.Font%2A> ottenere riferimenti <xref:System.Windows.Forms.Control.FontChanged> alla proprietà e all'evento.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8b1-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb8b1-123">Requirements</span></span>  
 <span data-ttu-id="bb8b1-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb8b1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb8b1-125">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb8b1-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb8b1-126">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb8b1-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb8b1-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb8b1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8b1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb8b1-128">See also</span></span>

- [<span data-ttu-id="bb8b1-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bb8b1-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bb8b1-130">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bb8b1-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
