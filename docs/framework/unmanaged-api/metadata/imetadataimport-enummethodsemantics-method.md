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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16cfa6df6251cd67860155cb8092e77a835eaaef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223270"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="5f74c-102">Metodo IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="5f74c-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="5f74c-103">Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="5f74c-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f74c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f74c-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f74c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f74c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5f74c-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="5f74c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5f74c-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="5f74c-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="5f74c-108">[in] Token MethodDef che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5f74c-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="5f74c-109">[out] Matrice utilizzata per archiviare le proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="5f74c-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5f74c-110">[in] Dimensione massima della matrice `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="5f74c-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="5f74c-111">[out] Il numero di eventi o proprietà restituite `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="5f74c-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f74c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f74c-112">Return Value</span></span>  
  
|<span data-ttu-id="5f74c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f74c-113">HRESULT</span></span>|<span data-ttu-id="5f74c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f74c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5f74c-115">`EnumMethodSemantics` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5f74c-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5f74c-116">Non esistono eventi o proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="5f74c-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="5f74c-117">In tal caso, `pcEventProp` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="5f74c-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f74c-118">Note</span><span class="sxs-lookup"><span data-stu-id="5f74c-118">Remarks</span></span>  
 <span data-ttu-id="5f74c-119">Molti tipi di common language runtime definiscono *proprietà* `Changed` eventi e `On` *proprietà* `Changed` metodi correlati nelle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f74c-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="5f74c-120">Ad esempio, il <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo definisce un <xref:System.Windows.Forms.Control.Font%2A> proprietà, un <xref:System.Windows.Forms.Control.FontChanged> evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="5f74c-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="5f74c-121">Il metodo della funzione di accesso set della <xref:System.Windows.Forms.Control.Font%2A> proprietà chiamate <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera il <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="5f74c-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="5f74c-122">È necessario chiamare `EnumMethodSemantics` utilizzando MethodDef per <xref:System.Windows.Forms.Control.OnFontChanged%2A> per ottenere riferimenti al <xref:System.Windows.Forms.Control.Font%2A> proprietà e il <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="5f74c-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f74c-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f74c-123">Requirements</span></span>  
 <span data-ttu-id="5f74c-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f74c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f74c-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5f74c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f74c-126">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5f74c-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f74c-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f74c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f74c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f74c-128">See also</span></span>

- [<span data-ttu-id="5f74c-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5f74c-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5f74c-130">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5f74c-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
